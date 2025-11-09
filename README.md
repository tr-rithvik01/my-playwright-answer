# Matrix Build CI/CD Demo

This repository demonstrates a modern CI/CD pipeline using GitHub Actions with matrix build strategy and artifact management.

## Contact Information
**Email:** 21f1002425@ds.study.iitm.ac.in

## Overview

This project showcases:
- ✅ Matrix build strategy with multiple OS and Node.js versions
- ✅ Parallel job execution
- ✅ Automated artifact generation and upload
- ✅ Build summaries and reporting

## Matrix Configuration

The workflow builds across:
- **Operating Systems:** Ubuntu, macOS, Windows
- **Node.js Versions:** 18, 20
- **Total Build Combinations:** 6 parallel jobs

## Artifacts Generated

Each matrix job generates unique artifacts with the naming pattern:
```
build-00c402b-<os-name>-node<version>
```

Examples:
- `build-00c402b-linux-node18`
- `build-00c402b-linux-node20`
- `build-00c402b-macos-node18`
- `build-00c402b-macos-node20`
- `build-00c402b-windows-node18`
- `build-00c402b-windows-node20`

Each artifact contains:
- `build-output.txt` - Detailed build information
- `build-info.json` - Structured build metadata

## Workflow Features

### Matrix Strategy
```yaml
strategy:
  matrix:
    os: [ubuntu-latest, macos-latest, windows-latest]
    node-version: [18, 20]
```

### Key Steps
1. **matrix-00c402b** - Identifier step for validation
2. Environment setup with Node.js
3. Build artifact generation
4. Artifact upload using `actions/upload-artifact@v4`
5. Summary report generation

## How to Use

1. **Fork this repository**
2. **Update README.md** with your email address
3. **Trigger the workflow:**
   - Push to `main` or `master` branch
   - Create a pull request
   - Manually trigger via "Actions" tab → "Run workflow"

4. **View Results:**
   - Go to "Actions" tab
   - Select the latest workflow run
   - Check "Artifacts" section for generated build outputs

## Workflow File

The complete workflow is located at: `.github/workflows/matrix-build.yml`

## Validation Checklist

- ✅ At least 3 successful matrix jobs
- ✅ At least 3 artifacts with `build-00c402b` prefix
- ✅ All artifacts contain actual content
- ✅ Step identifier `matrix-00c402b` present
- ✅ README.md contains email address

## Technical Details

### Artifact Contents

**build-output.txt:**
```
Build Information
==================
OS: ubuntu-latest
OS Name: linux
Node Version: 18
Build Date: 2025-11-09
Job ID: build
Run ID: <run-id>
==================
Build completed successfully!
```

**build-info.json:**
```json
{
  "os": "ubuntu-latest",
  "os_name": "linux",
  "node": "18",
  "timestamp": "2025-11-09T12:00:00Z",
  "status": "success"
}
```

## Troubleshooting

If workflows fail:
1. Check workflow logs in Actions tab
2. Verify Node.js version compatibility
3. Ensure branch names match trigger configuration
4. Review artifact upload permissions

## License

MIT License - Feel free to use this as a template for your own projects.

---

**Repository maintained for DevOps Challenge demonstration**
