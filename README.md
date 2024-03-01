# Book-Promp2
name: Character Development Workflow

on:
  pull_request:
    types: [opened, reopened, synchronize]

jobs:
  character_analysis:
    runs-on: ubuntu-latest
    steps:
      - name: Check out code
        uses: actions/checkout@v2
      
      - name: Setup Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.x'

      - name: Install dependencies
        run: |
          pip install -r requirements.txt
      
      - name: Run character analysis
        run: |
          python character_analysis.py
