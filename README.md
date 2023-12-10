# Hospital Management Canister

This repository contains the source code for a hospital management canister on the Internet Computer Protocol (ICP). The canister allows users to manage and query patients details, providing functionality such as adding, updating, deleting, and querying patient's details based on various criteria.

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Testing](#testing)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Overview

The hospital management canister is designed to be a decentralized solution for managing information about various patients. Each patient is represented by the `PatientDetails` struct, which includes fields such as `id`, `patient_name`, `patient_history`, `doctor_name`, `created_at`, `updated_at`, `next_appointment` and `in_clinic`. The canister uses a BTreeMap for efficient storage and retrieval of patients.

Key Features:

- **Querying**: Retrieve information about specific patient, all patients, patient in clinic, or perform a search based on a query string.

## Prerequisites

Before you begin, ensure that you have the following installed:

- [Rust](https://www.rust-lang.org/tools/install)
- [Internet Computer SDK](https://sdk.dfinity.org/docs/quickstart/local-quickstart.html)

## Installation

Clone the repository to your local machine:

```bash

```

## Usage

To use the hospital management canister, you can explore the provided query and update functions.

## Testing

To run tests, use the following command:

```bash
cargo test
```

## Deployment

To deploy the canister locally, follow these steps:

1. Start the canister:

   ```bash
   dfx start
   ```

2. Deploy the canister:

   ```bash
   dfx deploy
   ```

3. Use the generated canister identifier to interact with the deployed canister.

For additional deployment options and configurations, refer to the [Internet Computer SDK documentation](https://sdk.dfinity.org/docs/quickstart/local-quickstart.html).

## Contributing

Feel free to contribute to the project by submitting issues or pull requests. Follow the standard GitHub flow for contributing.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

dfx canister call icp_rust_boilerplate_backend add_patient '(
  record {
    patient_name = "sksk";
    patient_history = "jssk";
    doctor_name = "jjs";
    next_appointment = 2384754;
    in_clinic = true;
  }
)'

dfx canister call icp_rust_boilerplate_backend get_available_patients '()'
dfx canister call icp_rust_boilerplate_backend sort_patient_by_name '()'
dfx canister call icp_rust_boilerplate_backend search_patients '("sksk")'
dfx canister call icp_rust_boilerplate_backend search_doctors '("jjsks")'
dfx canister call icp_rust_boilerplate_backend set_next_appointment '(1, 878888)'

dfx canister call icp_rust_boilerplate_backend update_patient '(0, record { patient_name = "sksk";
    patient_history = "jssk";
    doctor_name = "sks";
    next_appointment = 2384754;
    in_clinic = true; })'

dfx canister call icp_rust_boilerplate_backend get_patient '(1)'
dfx canister call icp_rust_boilerplate_backend mark_patient_not_in_clinic '(1)'
dfx canister call icp_rust_boilerplate_backend get_patient_update_history '(1)'
sort_patient_by_name()

dfx canister call icp_rust_boilerplate_backend add_patient '(
  record {
    patient_name = "jane";
    patient_history = "jssk";
    doctor_name = "jjsks";
    next_appointment = 2384754;
    in_clinic = true;
  }
)'