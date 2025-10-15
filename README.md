# The shared actions and workflows for the organization

## Usage
### Searching for secrets
need grant the repository access to the organization secret https://github.com/organizations/anyproto/settings/secrets/actions/SLACK_WEBHOOK_URL_ALERTS
```
cat <<EOF > .github/workflows/secret-scanner.yml
---
name: Searching for secrets

on:
  - push
  - pull_request

jobs:
  secret-scanner-reusable:
    uses: anyproto/shared-actions/.github/workflows/secret-scanner-reusable.yml@v1
    secrets: inherit # pass all secrets
EOF
```

## Update release tag
the version in RELEASE must always be new !!!
```
RELEASE='v1.0.0'; git fetch -pP && git tag "$RELEASE" && git push --tags && git tag -f v1 && git push origin -f v1
```

## Contribution
Thank you for your desire to develop Anytype together!

❤️ This project and everyone involved in it is governed by the [Code of Conduct](https://github.com/anyproto/.github/blob/main/docs/CODE_OF_CONDUCT.md).

🧑‍💻 Check out our [contributing guide](https://github.com/anyproto/.github/blob/main/docs/CONTRIBUTING.md) to learn about asking questions, creating issues, or submitting pull requests.

🫢 For security findings, please email [security@anytype.io](mailto:security@anytype.io) and refer to our [security guide](https://github.com/anyproto/.github/blob/main/docs/SECURITY.md) for more information.

🤝 Follow us on [Github](https://github.com/anyproto) and join the [Contributors Community](https://github.com/orgs/anyproto/discussions).

---
Made by Any — a Swiss association 🇨🇭
Licensed under [LICENSE NAME](./LICENSE.md).
