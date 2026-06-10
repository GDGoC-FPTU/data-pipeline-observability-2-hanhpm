[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112943&assignment_repo_type=AssignmentRepo)

# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** maihanhpham.coco@gmail.com  
**Name:** Pham Mai Hanh

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian bang Python va pandas. Pipeline doc du lieu tu `raw_data.json`, loai bo record khong hop le, chuan hoa category, tinh gia sau khi giam 10%, them timestamp xu ly, va luu ket qua vao `processed_data.csv`. Bai lab cung co phan stress test de so sanh tac dong cua clean data va garbage data len cau tra loi cua agent.

---

## Cach chay (How to Run)

### Prerequisites

```bash
pip install pandas pytest
```

### Chay ETL Pipeline

```bash
python solution.py
```

Output da chay:

```text
Extracted 5 records.
Validation complete. Valid: 3, Errors: 2
Pipeline completed! 3 records saved.
```

### Chay Agent Simulation (Stress Test)

```bash
python generate_garbage.py
python agent_simulation.py
```

Output stress test:

```text
Testing with CLEAN data:
Agent: Based on my data, the best choice is Laptop at $1200.

Testing with GARBAGE data:
Agent: Based on my data, the best choice is Nuclear Reactor at $999999.
```

---

## Cau truc thu muc

```text
solution.py              # ETL pipeline script
raw_data.json            # Input data
processed_data.csv       # Clean output cua pipeline
generate_garbage.py      # Tao garbage_data.csv
agent_simulation.py      # So sanh agent voi clean va garbage data
experiment_report.md     # Bao cao thi nghiem
README.md                # File nay
tests/test_autograder.py # Autograder tests
```

---

## Ket qua

Pipeline da doc 5 records tu `raw_data.json`. Sau validation, co 3 records hop le duoc giu lai va 2 records khong hop le bi loai bo do `price <= 0` hoac `category` rong. File `processed_data.csv` da duoc tao voi cac cot `discounted_price` va `processed_at`.

Stress test cho thay clean data giup agent chon san pham hop ly la Laptop, trong khi garbage data lam agent chon Nuclear Reactor do outlier gia qua lon trong category electronics.
