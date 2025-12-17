# On Multi-Marginal Partial Optimal Transport (MMPOT)

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Repository này chứa poster, slide và docs cho đề tài nghiên cứu: **"On Multi-Marginal Partial Optimal Transport: Rectifying Infeasible Extension Strategies and Efficient Primal-Dual Methods"**.
Nhóm bao gồm Hoàng Đức Dũng và Nguyễn Đình Thiên Quang trong môn CS519.Q11

## 📌 Giới thiệu (Overview)

Nghiên cứu này giải quyết các vấn đề tồn đọng trong bài toán Vận chuyển Tối ưu Bộ phận Đa biên (MMPOT):
1.  **Chỉ ra sai lầm:** Chứng minh các chiến lược mở rộng điểm giả (dummy point extension) hiện tại dẫn đến nghiệm **không khả thi (infeasible)** về mặt toán học.
2.  **Đề xuất giải pháp:** Giới thiệu công thức **Đối ngẫu (Dual Formulation)** mới không cần mở rộng tensor.
3.  **Thuật toán tối ưu:** Cung cấp các thuật toán giải (solvers) đạt tốc độ hội tụ $\mathcal{O}(1/\epsilon)$.

## 🚀 Các thuật toán (Algorithms)

Repo này bao gồm việc cài đặt các thuật toán sau:

* **GreenkhornMMPOT:** Thuật toán tham lam (Greedy coordinate descent) cải tiến cho MMPOT.
* **PDAAM:** Primal-Dual Accelerated Alternating Minimization.
* **APDAGD:** Adaptive Primal-Dual Accelerated Gradient Descent.
* **Rounding Algorithm:** Thuật toán làm tròn mới đảm bảo nghiệm thỏa mãn ràng buộc khối lượng.
