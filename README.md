# Terraform module generator

<a href='https://ko-fi.com/O4O0RSHV' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi3.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

Scaffolding for new Terraform module projects

### Features

- `main.tf`, `variables.tf`,`outputs.tf` files to module root path

- `.editorconfig`, `.gitignore`, `.gitattributes` and `.terraform-version` files to module root path

- Option to choose test frameworks

  - [Terratest](https://github.com/gruntwork-io/terratest)
  - [kitchen-terraform](https://github.com/newcontext-oss/kitchen-terraform)

- `test` directory with an example test based on test framework selection

- `.pre-commit-config.yaml` for `terraform fmt`, `terraform-docs`, `check-merge-conflict` and (`go fmt`, `golint`) / `rubocop`

- `example` directory with module usage tf files

### Prerequisites

- [terraform](https://learn.hashicorp.com/terraform/getting-started/install#installing-terraform) `pro tip: use tfenv`
- [terraform-docs](https://github.com/segmentio/terraform-docs)
- [pre-commit](https://pre-commit.com/#install)
- For tests
  - **terratest**
    - [golang](https://golang.org/doc/install#install) `pro tip: use gvm`
    - [golint](https://github.com/golang/lint#installation)
  - **kitchen-terraform**
    - [ruby](https://rvm.io/) `pro tip: use rvm`

### Installation

1. Install [nodejs](https://nodejs.org/en/download/) `pro tip: use nvm`

2. Install Yeoman

```sh
npm install -g yo
```

3. Install this generator

```shell
npm install -g generator-tf-module
```

### Usage

To use the included generator execute the below command in shell and provide your new module name for the prompt

```sh
> yo tf-module
...
? Enter name for the new terraform module :  example-module
? Enter description for the new terraform module :  A new terraform module
? Enter author name :  sudokar
? Choose test framework (Use arrow keys)
❯ Terratest
  kitchen-terraform
```

Project layout generated for the new module with _Terratest_ selection

```
example-module
├── .editorconfig
├── .gitattributes
├── .gitignore
├── .pre-commit-config.yaml
├── .terraform-version
├── README.md
├── main.tf
├── outputs.tf
├── variables.tf
├── example
│   ├── main.tf
│   ├── outputs.tf
│   └── variables.tf
├── test
    └── example_test.go
```

Project layout generated for the new module with _kitchen-terraform_ selection

```
example-module
├── .editorconfig
├── .gitattributes
├── .gitignore
├── .pre-commit-config.yaml
├── .terraform-version
├── .ruby-version
├── .kitchen.yml
├── Gemfile
├── README.md
├── main.tf
├── outputs.tf
├── variables.tf
├── example
│   ├── main.tf
│   ├── outputs.tf
│   └── variables.tf
├── test
    └── integration
        └── default
            └── example_spec.rb
```

##### Post generation steps

Step 1

On the generated module's root path, Initialize git repository

```sh
git init
```

Step 2

On the generated module's root path, Install pre-commit hooks

```sh
pre-commit install
```

Step 3 (Applicable only for `terratest`)

For golang tests, get below libs

```sh
> go get github.com/gruntwork-io/terratest/modules/terraform
> go get github.com/stretchr/testify/assert
```

### Support my project

<a href='https://ko-fi.com/O4O0RSHV' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi4.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>  
To support maintenance of this project, <a href='https://ko-fi.com/O4O0RSHV'>Buy Me a Coffee</a>

### Contribution

Found a bug? feel free to raise an issue.  
Pull requests are always welcome. Keen to review and merge asap.

### Maintainers

This project is maintained by [sudokar](https://github.com/sudokar)

### License

MIT

#### Keywords

[terraform](https://www.npmjs.com/search?q=keywords:terraform) [scaffolding](https://www.npmjs.com/search?q=keywords:scaffolding) [yeoman](https://www.npmjs.com/search?q=keywords:yeoman) [terraform module](https://www.npmjs.com/search?q=keywords:terraform%20module)
