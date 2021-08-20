# Google Summer of Code 2021 
---
## Develop a Shared Data Resource Docused on Dependencies, Risks and Vulnerability in Open Source Software
### Project Abstract
Augur is a software suite for collecting and measuring structured data about free and open-source software (FOSS) communities. The aim of my project was to implement various tools that that examine package manager data for the languages in use (e.g., package.json for JavaScript npm, pyproject.toml / requirements.txt for Python, Gemfile / Gemfile.lock for Ruby).

### Coding Phase 1 
This phase began by understanding Augur's architecture and all the workers. Then I started working on the current Deps Worker which is responsible to collect dependencies data by looking at the import statements of the code file. I extended the current Deps worker to gather **OSSF Scorecard** data for reposiories. This included adding to current installation script to set necessary environment for scorecard to generate data and calling scorecard from the deps worker. Scorecard generates a list of tests for a repository with score and status for each test.

### Coding Phase 2 
This phase was about building a new worker for augur to calculate the **libyear**. Initially we thought to implment existing libyear tools, but due to their limitation we decided to build a tool of our own. Currently, Libyear Worker is fully supporing PYPI package manager with supporting file formats as -

- Requirements.txt
- setup.py
- Pipfile
- Pipfile.lock
- poetry
- poetry.lock
- environment.yml
- environment.yaml
- environment.yml.lock
- environment.yaml.lock

