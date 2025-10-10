# Deobfuscation Dashboard

This dashboard tracks the progress of deobfuscation

## Live Dashboard

Once GitHub Pages is enabled, the dashboard will be available at:
`https://rubybrowncoat.github.io/dashboard/`

## What's Being Tracked

The dashboard monitors deobfuscation progress across five categories:

- **Classes**: C# classes (e.g., `Class1211`, `GClass104`)
- **Methods**: Method names (e.g., `method_123`)
- **Fields**: Field and variable names (e.g., `field_456`, `textBox1`)
- **Enums**: Enumeration types (e.g., `GEnum42`)
- **Enum Values**: Enumeration values (e.g., `const_0`)

## How It Works

1. **Analysis Script**: The `static-analysis/regex-analysis.mjs` script scans all C# files in the project
2. **Data Generation**: It generates `docs/deobfuscation-progress.json` with current statistics
3. **Visualization**: The `docs/index.html` dashboard displays the data with progress bars
4. **Automation**: GitHub Actions automatically updates the dashboard when C# files are changed

## Data Format

The JSON file contains:

```json
{
  "timestamp": "2024-01-01T00:00:00.000Z",
  "categories": {
    "classes": {
      "total": 1000,
      "obfuscated": 500,
      "deobfuscated": 500,
      "percentComplete": 50
    },
    ...
  },
  "overall": {
    "total": 5000,
    "obfuscated": 2500,
    "deobfuscated": 2500,
    "percentComplete": 50
  }
}
```
