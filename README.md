# Mock Lambda API

## Overview

This project provides a mock server for simulating API requests and responses using AWS Lambda functions, primarily for performance testing purposes. The structure of the project is set up so that it can be reused for other API endpoints and by taking advantage of tools, templates and code already built, the time to build a new mock will be significantly decreased.

## Table of Contents

- [Mock Lambda API](#mock-lambda-api)
  - [Overview](#overview)
  - [Table of Contents](#table-of-contents)
  - [Setup](#setup)
    - [Prerequisites](#prerequisites)
    - [Configuration](#configuration)
  - [Usage](#usage)
    - [CIS2 Mock](#cis2-mock)
    - [Testing](#testing)
  - [Design](#design)
  - [Contributing](#contributing)
  - [Contacts](#contacts)
  - [Licence](#licence)

## Setup

Clone the repository

```shell
git clone https://github.com/NHSDigital/mock-lambda-api.git
cd mock-lambda-api
```

### Prerequisites

The following software packages, or their equivalents, are expected to be installed and configured:

- [Docker](https://www.docker.com/) container runtime or a compatible tool, e.g. [Podman](https://podman.io/),
- [asdf](https://asdf-vm.com/) version manager,
- [GNU make](https://www.gnu.org/software/make/) 3.82 or later,

> [!NOTE]<br>
> The version of GNU make available by default on macOS is earlier than 3.82. You will need to upgrade it or certain `make` tasks will fail. On macOS, you will need [Homebrew](https://brew.sh/) installed, then to install `make`, like so:
>
> ```shell
> brew install make
> ```
>
> You will then see instructions to fix your [`$PATH`](https://github.com/nhs-england-tools/dotfiles/blob/main/dot_path.tmpl) variable to make the newly installed version available. If you are using [dotfiles](https://github.com/nhs-england-tools/dotfiles), this is all done for you.

- [GNU sed](https://www.gnu.org/software/sed/) and [GNU grep](https://www.gnu.org/software/grep/) are required for the scripted command-line output processing,
- [GNU coreutils](https://www.gnu.org/software/coreutils/) and [GNU binutils](https://www.gnu.org/software/binutils/) may be required to build dependencies like Python, which may need to be compiled during installation,

> [!NOTE]<br>
> For macOS users, installation of the GNU toolchain has been scripted and automated as part of the `dotfiles` project. Please see this [script](https://github.com/nhs-england-tools/dotfiles/blob/main/assets/20-install-base-packages.macos.sh) for details.

- [Python](https://www.python.org/) required to run Git hooks,
- [`jq`](https://jqlang.github.io/jq/) a lightweight and flexible command-line JSON processor.

### Configuration

Installation and configuration of the toolchain dependencies

```shell
make config
```

## Usage

To use the mock stub locally you must have the docker container running. Here are some examples of requests to access the endpoints in this repository:

### CIS2 Mock

To access the API endpoints using Guzzle HTTP client in PHP, follow these steps

<!-- Provisionally - likely to change as developing -->

1) **Install Guzzle**

    ```shell
    composer require guzzlehttp/guzzle
    ```

2) **Ensure your environment** is 'local-test' so that when the API call is made it hits the mock endpoint , not prod or non-prod.
3) **Use the Existing PHP Script:** Use the PHP script from the other repository to make requests to the mock API endpoints. Ensure the script is configured to point to the mock server running locally.
4) **Start the Mock Server:** Ensure the mock server is running locally. You can start the server using the following command:

   ```shell
   npm start
   ```

5) **Update the API Endpoint:** Update the API endpoint in your tests to point to the mock server. For example, if the mock server is running on `http://localhost:3000`, update the endpoint URLs in your tests accordingly.

### Testing

TBC

## Design

TBC

## Contributing

TBC

## Contacts

TBC

To get in contact with the owners of this project please **email** [england.ftrs-live-directory@nhs.net](mailto:england.ftrs-live-directory@nhs.net) or message on the following **slack channels**: [dos-devs](https://nhsdigitalcorporate.enterprise.slack.com/archives/CTZ3M4L7Q)  or [ftrs-live-directory](https://nhsdigitalcorporate.enterprise.slack.com/archives/).

## Licence

TBC

> The [LICENCE.md](./LICENCE.md) file will need to be updated with the correct year and owner

Unless stated otherwise, the codebase is released under the MIT License. This covers both the codebase and any sample code in the documentation.

Any HTML or Markdown documentation is [© Crown Copyright](https://www.nationalarchives.gov.uk/information-management/re-using-public-sector-information/uk-government-licensing-framework/crown-copyright/) and available under the terms of the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).
