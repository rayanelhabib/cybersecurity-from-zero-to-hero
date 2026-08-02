```bash
Get-ChildItem -Recurse -Directory | ForEach-Object {
    $gitkeepPath = Join-Path $_.FullName ".gitkeep"
    if (-not (Test-Path $gitkeepPath)) {
        New-Item -ItemType File -Path $gitkeepPath -Force | Out-Null
    }
}
```