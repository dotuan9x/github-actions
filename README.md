# GitHub Actions for Create React App

### Tạo và sử dụng github actions
Trong folder repository của dự án, ta tạo folder `.github/workflows/`

Tiếp đó ta tạo file `.yml` bất kỳ, ví dụ `qc.yml` để cấu hình [github actions](https://docs.github.com/en/actions/using-workflows/about-workflows#create-an-example-workflow) deploy lên môi trường qc


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

# Kích hoạt workflow khi đánh tags với prefix qc.*
on:
  push:
    tags:
      - qc.*
        
# Tạo schedule để kích hoạt workflow => https://docs.github.com/en/actions/learn-github-actions/events-that-trigger-workflows#schedule       
```

Danh sách các actions của GitHub: https://github.com/marketplace


