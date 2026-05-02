# Computational Research Workflows Homework

Homework repository for the DSSE Computational Research Workflows course.

The project demonstrates a small reproducible workflow: a Python `Wallet` class, a pytest test suite, a container definition, and continuous-integration scaffolding.

## Repository Layout

- `wallet.py` - simple wallet implementation.
- `test_wallet.py` - pytest tests for the wallet behavior.
- `Dockerfile` - course environment for running the test suite.
- `.github/workflows/test.yml` - GitHub Actions workflow, when present, for automated test execution.
- `.dockerignore` - excludes local Python and Git artifacts from image build context.

## Local Python Usage

```bash
python -m pytest
```

The test suite checks:

- default wallet balance
- custom initial balance
- adding cash
- spending cash
- rejecting overspending with `InsufficientAmount`

## Container Usage

```bash
docker build -t computational-workflows-homework .
docker run --rm computational-workflows-homework py.test-3
```

The original course used Docker Hub tagging and GitHub Actions as part of the assignment. Keep those commands in Git history if you need the exact submitted workflow.

## Notes

- This is a small course exercise, not a reusable wallet library.
- Generated Python caches and pytest caches are ignored.
- The Dockerfile is intentionally simple because it mirrors the course exercise rather than a production deployment.
