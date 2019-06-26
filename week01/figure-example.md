---
title: Example Figure
layout: figure-vega-lite
---

{
  "$schema": "https://vega.github.io/schema/vega-lite/v3.json",
  "data": {
      "url": "../data/yt_repo.json"
  },
  "transform": [
      {
          "timeUnit": "yearquarter",
          "field": "committed_datetime",
          "as": "commit_quarter"
      },
      {"aggregate": [ {"op": "count", "as":"count"} ],
          "groupby": ["commit_quarter", "author"] }
  ],
  "hconcat": [
      {
          "selection": {
              "commit_range": {
                  "type": "interval",
                  "encodings": ["x"]
              }
          },
          "mark": "bar",
          "encoding": {
              "y": {
                  "aggregate": "sum",
                  "field": "count",
                  "type": "quantitative",
                  "axis": {"title": "# commits"}
              },
              "x": {
                  "field": "commit_quarter",
                  "type": "temporal",
                  "scale": {
                      "padding": 0
                  }
              }
          },
          "config": {
              "axis": {"shortTimeLabels": true}
          }
      },
      {
          "transform": [
              {"filter": {"selection": "commit_range"}},
              {"aggregate": [{"op": "sum", "field": "count", "as":"author_count"}], "groupby": ["author"] },
              {"window": [{ "op": "rank", "as": "rank" }],
                  "sort": [{"order": "descending", "field": "author_count"}]},
              {"filter": {"field": "rank", "lte": 10}},
              {"calculate": "split(datum['author'], ' <', 1)[0]", "as": "author_name"}
          ],
          "mark": {"type": "bar"},
          "encoding": {
              "y": {
                  "field": "author_name",
                  "type": "nominal",
                  "axis": {"title": "top 10 authors"},
                  "sort": {"order": "ascending", "field": "rank"}
              },
              "x": {
                  "type": "quantitative",
                  "field": "author_count",
                  "axis": {"title": "number of commits"}
              }
          }
      }
  ],
  "config": {
      "axis": {
          "labelFontSize": 16,
          "titleFontSize": 16
      },
      "legend": {
          "labelFontSize": 16,
          "titleFontSize": 16
      }
  }
}
