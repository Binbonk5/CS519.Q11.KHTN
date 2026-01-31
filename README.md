# CS519.Q11.KHTN - Research Methodology


## 📌 Project Title (Vietnamese)
**VẬN CHUYỂN TỐI ƯU BỘ PHẬN ĐA BIÊN: KHẮC PHỤC CHIẾN LƯỢC MỞ RỘNG KHÔNG KHẢ THI VÀ CÁC PHƯƠNG PHÁP PRIMAL-DUAL HIỆU QUẢ**

## 📌 Project Title (English)
**ON MULTI-MARGINAL PARTIAL OPTIMAL TRANSPORT: RECTIFYING INFEASIBLE EXTENSION STRATEGIES AND EFFICIENT PRIMAL-DUAL METHODS**

---

🎓 **Instructor**
- PGS.TS.Lê Đình Duy

---

## 👥 Team Members
- **Nguyễn Đình Thiên Quang** - 23521285
- **Hoàng Đức Dũng** - 23520328
---

## 🔗 Project Structure
- **Slides:** CS519.Q11.DeCuong.FinalReport.Slide.pdf
- **Proposal:** CS519.Q11.DeCuong.FinalReport.Doc.pdf
- **Poster:** CS519.Q11.DeCuong.FinalReport.Poster.pdf
- **Youtube:** [Link](https://www.youtube.com/watch?v=oJYt4nf3nJU)

---

## 🌸 Abstract
Bài toán Vận chuyển Tối ưu Bộ phận Đa biên (MMPOT) là công cụ mạnh mẽ để xử lý dữ liệu nhiễu và không cân bằng trong Học máy. Tuy nhiên, các phương pháp hiện tại chủ yếu dựa vào **Chiến lược mở rộng (Extension Strategies)** bằng cách thêm điểm giả (dummy points). 

Nghiên cứu này chỉ ra rằng chiến lược trên dẫn đến các lời giải **không khả thi (infeasible)** về mặt toán học do vi phạm ràng buộc tổng khối lượng khi áp dụng điều chuẩn Entropy. Đồng thời, chúng gây ra sự bùng nổ về độ phức tạp tính toán ($\mathcal{O}(1/\epsilon^4)$). Để giải quyết vấn đề này, đề tài đề xuất một **khung Primal-Dual mới** không cần mở rộng tensor, đi kèm với các thuật toán tăng tốc (PDAAM, APDAGD) đạt tốc độ hội tụ tối ưu lý thuyết ($\mathcal{O}(1/\epsilon)$), đảm bảo tính chính xác và hiệu quả cao.

---

## 🎯 Research Objectives

### Mục tiêu tổng quát
Xây dựng một hệ thống lý thuyết và thuật toán hoàn chỉnh để giải quyết bài toán MMPOT một cách chính xác về mặt toán học và tối ưu về mặt chi phí tính toán.

### Mục tiêu cụ thể
- **Chứng minh tính bất khả thi:** Phân tích toán học để bác bỏ tính hiệu quả của các chiến lược mở rộng điểm giả hiện tại (SOTA).
- **Xây dựng công thức Đối ngẫu mới:** Thiết lập bài toán tối ưu đối ngẫu trơn (smooth dual) trực tiếp cho MMPOT mà không cần mở rộng tensor.
- **Phát triển thuật toán tốc độ cao:** Cài đặt và tối ưu hóa 3 thuật toán:
  + GreenkhornMMPOT (Tham lam)
  + PDAAM (Tăng tốc Primal-Dual)
  + APDAGD (Gradient Descent thích nghi)
- **Thực nghiệm:** Kiểm chứng hiệu quả trên bài toán Partial Barycenter với dữ liệu ảnh MNIST.

---

## 🖊️ Methodology

### 1️⃣ Phân tích sự bất khả thi (Infeasibility Analysis)
- Chứng minh rằng tính phi tuyến của **Entropic Regularization** ngăn cản việc điều chỉnh khối lượng chính xác tại các biên khi dùng điểm giả.
- Chỉ ra độ phức tạp của thuật toán Sinkhorn cũ tăng vọt lên mức $\mathcal{O}(1/\epsilon^4)$ hoặc hàm mũ khi số biên $m \ge 4$.

### 2️⃣ Công thức Đối ngẫu mới (Novel Dual Formulation)
- Mô hình hóa bài toán gốc với các biến bù (slack variables).
- Chuyển đổi sang bài toán đối ngẫu lồi mạnh và trơn.
- Chứng minh **Cận trên mới (Novel Upper Bound)** cho chuẩn $L_\infty$ của nghiệm tối ưu, làm cơ sở cho sự hội tụ của thuật toán.

### 3️⃣ Thuật toán & Làm tròn (Algorithms & Rounding)
- **Rounding:** Sử dụng quy trình "Enforcing Procedure" để chiếu nghiệm gần đúng về tập khả thi, đảm bảo sai số khối lượng được kiểm soát ($23\epsilon$).
- **Solvers:** Áp dụng kỹ thuật tăng tốc Nesterov và cập nhật tham lam (Greedy update) để đạt tốc độ hội tụ $\mathcal{O}(1/\epsilon)$.

---

## 📊 Expected Outcomes
- Một khung lý thuyết chứng minh rõ ràng sai lầm của các phương pháp cũ.
- Bộ thuật toán (Greenkhorn, PDAAM, APDAGD) chạy nhanh hơn và chính xác hơn các baseline hiện tại.
- Ứng dụng thành công trong việc lọc nhiễu (outliers) cho bài toán tính toán tâm tỉ cự (Barycenter) trên dữ liệu ảnh.

---

## 📚 References
[1] Anh Duc Nguyen, Tuan Dung Nguyen, Quang Minh Nguyen, Hoang H. Nguyen, Lam M. Nguyen, Kim-Chuan Toh. On partial optimal transport: Revising the infeasibility of sinkhorn and efficient gradient methods. *AAAI* 2024: 14387-14395.

[2] Tianyi Lin, Nhat Ho, Marco Cuturi, Michael I. Jordan. On the Complexity of Approximating Multimarginal Optimal Transport. *J. Mach. Learn. Res.* 23: 65:1-65:43 (2022).

[3] Khang Le, Huy Nguyen, Khai Nguyen, Tung Pham, Nhat Ho. On Multimarginal Partial Optimal Transport: Equivalent Forms and Computational Complexity. *AISTATS* 2022: 4397-4413.

[4] Marco Cuturi. Sinkhorn Distances: Lightspeed Computation of Optimal Transport. *NIPS* 2013: 2292-2300.

[5] Pavel Dvurechensky, Alexander Gasnikov, Alexey Kroshnin. Computational Optimal Transport: Complexity by Accelerated Gradient Descent Is Better Than by Sinkhorn's Algorithm. *ICML* 2018: 1366-1375.
