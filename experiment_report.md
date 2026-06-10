# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** maihanhpham.coco@gmail.com  
**Name:** Pham Mai Hanh  
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate va transform, nen agent chon san pham electronics co gia cao nhat trong clean data. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Garbage data co outlier rat lon trong category electronics, lam agent dua ra goi y khong hop ly. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai khi dung garbage data vi no phu thuoc truc tiep vao chat luong du lieu dau vao. Trong file `garbage_data.csv`, du lieu co duplicate ID, sai kieu du lieu nhu price bang chu, outlier rat lon nhu Nuclear Reactor gia 999999, va gia tri null. Logic cua agent chi loc category electronics va chon dong co price cao nhat, nen outlier se thang du ket qua do khong hop ly. Neu du lieu khong duoc validate truoc, prompt tot van khong the sua duoc tri thuc sai trong bang du lieu. Vi vay, data cleaning va observability rat quan trong truoc khi dua du lieu vao he thong AI.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot co the huong dan agent cach tra loi, nhung neu du lieu nguon bi sai, thieu, trung lap, hoac co outlier, agent van co the dua ra ket qua sai. Chat luong du lieu la nen tang de agent tra loi dung va dang tin cay.
