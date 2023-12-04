
### Contributing Guidelines
Ensure that you adhere to the following guidelines:

* Should be about principles and concepts that can be applied in any company or individual project. Do not focus on particular tools or tech stack(which usually change over time).
* Adhere to the [Code of Conduct](./CODE_OF_CONDUCT.md)
* Should be relevant to the roles and responsibilities of Linux.
* Should be locally tested (see steps for testing) and well formatted.

### Building and testing locally
Run the following commands to build and view the site locally before opening a PR.

```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs build
mkdocs serve
```
