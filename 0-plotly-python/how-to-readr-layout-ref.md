# How to Read the Plotly Layout Reference

  **\# from Claude**
## Parameter Tree Structure

Each parameter in the reference shows **3 things**:

```
title                                           ← parameter name
Code: fig.update_layout(title=dict(...))        ← copy and use directly
Type: dict containing...                        ← if dict = has sub-parameters inside
  └── font                                      ← sub-parameter
       Code: fig.update_layout(title_font=dict(...))
       └── size                                 ← sub-sub-parameter
            Code: fig.update_layout(title_font_size=<VALUE>)  ✅ ready to use
```

---

## Key Rule — Always Read the Deepest `Code:` Line

You don't need to understand every nested level.
Just find the **deepest `Code:` line** and copy it directly. For example:

```python
# Tree path:  title → font → size
fig.update_layout(title_font_size=20)

# Tree path:  xaxis → tickfont → color
fig.update_layout(xaxis_tickfont_color="red")

# Tree path:  legend → bgcolor
fig.update_layout(legend_bgcolor="white")
```

> **Pattern:** Replace every `.` in the tree path with `_`

---

## Quick Tip — Use Ctrl+F

The page is very long. Instead of reading everything, just press **Ctrl+F** and search for what you need:

| Want to change | Search for |
|---|---|
| Background color | `bgcolor` |
| Tick rotation | `tickangle` |
| Grid lines | `showgrid` |
| Font size | `font_size` |
| Legend position | `legend` |