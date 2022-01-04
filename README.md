# GitHub Actions for Create React App

### Sự kiện trigger workflow

```shell
# Kích hoạt workflow khi push code lên branch
on: push

# Kích hoạt workflow khi push hoặc tạo pull request
on: [push, pull_request]

# Kích hoạt workflow khi push code lên branch master hoặc tạo pull request trên branch master
on:
  # Trigger the workflow on push or pull request,
  # but only for the main branch
  push:
    branches:
      - main
  pull_request:
    branches:
      - main
  # Also trigger on page_build, as well as release created events
  page_build:
  release:
    types: # This configuration does not affect the page_build event above
      - created

# Tạo schedule để kích hoạt workflow => https://docs.github.com/en/actions/learn-github-actions/events-that-trigger-workflows#schedule       
```

Danh sách các actions của GitHub: https://github.com/marketplace


