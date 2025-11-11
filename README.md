# Solar Challenge — Week 0

Data profiling and exploratory data analysis (EDA) for solar radiation measurement data collected for Benin, Sierra Leone, and Togo.

This repository contains the environment setup, data organization, notebooks, and supporting code used during Week 0 of the Solar Radiation Measurement Project.

---

Table of contents
- Project overview
- What's included
- Folder structure
- Environment setup
- How to run the notebooks
- Data handling notes
- Testing
- CI / GitHub Actions
- Contributing
- License
- Contact

---

Project overview
This project contains early-stage work to profile and explore solar radiation measurement datasets for three countries (Benin, Sierra Leone, and Togo). The focus in Week 0 was on setting up a reproducible development environment (Conda + requirements.txt), organizing raw and processed data, and producing EDA notebooks that summarize data quality, distributions, missingness, and basic time-series characteristics.

What's included
- A modular folder layout with clear separation of raw and processed data for each country.
- Jupyter notebooks with EDA for each country.
- A requirements.txt to reproduce the environment.
- A GitHub Actions CI workflow that validates the environment and installs dependencies on pushes/PRs.

Folder structure
<img width="993" height="1066" alt="image" src="https://github.com/user-attachments/assets/90f9cb9f-6da6-4af8-b89a-e237778d2f91" />


Environment setup (Task 1 — Git & Environment Setup)
To ensure reproducible environments, a dedicated Conda environment was used and all dependencies are pinned in requirements.txt.

1. Create and activate the Conda environment (recommended)
   - conda create -n solar-challenge-week0 python=3.12 -y
   - conda activate solar-challenge-week0

2. Install dependencies
   - pip install -r requirements.txt

(If you prefer an environment.yml, you can generate one from your conda environment:
   - conda env export --name solar-challenge-week0 --file environment.yml
)

Running notebooks
- Launch JupyterLab or Jupyter Notebook from the repo root:
  - jupyter lab
  - or
  - jupyter notebook
- Open the notebooks in the notebooks/ directory (benin_eda.ipynb, sierraleone.ipynb, togo.ipynb).
- Notebooks assume you have placed raw data in the appropriate data/<country>/raw/ subfolders.

Data handling notes
- Large datasets and local IDE settings are excluded from version control via .gitignore.
- Keep raw data immutable; write any cleaning/transformation outputs to data/<country>/processed/.
- If you add new data, update any notebook paths or helper scripts accordingly.

Testing
- Unit tests are located in the tests/ directory.
- Run tests with pytest:
  - pytest -q

CI / GitHub Actions
A CI pipeline is configured at .github/workflows/ci.yaml to:
- Verify the Python version (3.12).
- Install dependencies from requirements.txt on push and pull requests.
- Ensure reproducible environments for contributors.

Contributing
- Please open issues for bugs or feature requests.
- Create a new branch for changes: git checkout -b fe--at/your-feature
- Keep commits small and descriptive. Follow the existing commit history style.
- Open a Pull Request describing your changes and link related issues.

Recommended next steps for collaborators
- Add data validation and ingestion scripts in scripts/ for reproducible preprocessing.
- Add a small example script in src/ showing how to load processed data and produce the main EDA charts outside notebooks (useful for CI).
- Extend CI to run unit tests and linting on PRs.
- Consider adding a sample (small) dataset or synthetic dataset for CI-friendly notebook testing.

License
This project is licensed under the terms contained in the LICENSE file.

Contact
Repository owner: MYGBM
For questions or collaboration, please open an issue or contact the repo owner via their GitHub profile.
