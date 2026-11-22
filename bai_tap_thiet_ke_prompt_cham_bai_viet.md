# BÀI TẬP THỰC HÀNH: THIẾT KẾ PROMPT AI CHẤM ĐIỂM ĐOẠN VĂN THEO RUBRIC

## 1. Phân tích bài toán
Để giúp giảng viên chấm điểm bài luận ngắn khoảng 300 từ một cách khách quan, nhất quán và có căn cứ rõ ràng thay vì nhận xét chung chung, em đã thiết kế một Prompt đóng vai **Giảng viên đại học nghiêm khắc nhưng công tâm**. Prompt này ép buộc AI phải tuân thủ tuyệt đối bảng tiêu chí (Rubric) cho trước, trích dẫn nguyên văn câu chữ trong bài làm minh chứng cho từng mức điểm và đưa ra gợi ý sửa lỗi cụ thể.

---

## 2. Thiết kế Prompt hoàn chỉnh

Dưới đây là câu lệnh (Prompt) em đã xây dựng để đáp ứng đầy đủ các ràng buộc dữ liệu và yêu cầu nghiệp vụ:

```text
# VAI TRÒ (ROLE)
Bạn là một Giảng viên đại học có chuyên môn cao, công tâm, khách quan và chi tiết. Nhiệm vụ của bạn là đọc, đánh giá và chấm điểm đoạn văn nghị luận (khoảng 300 từ) của sinh viên với chủ đề: "Vai trò của AI trong hoạt động học tập của sinh viên đại học".

# QUY TẮC BẮT BUỘC (CONSTRAINTS)
1. Tuyệt đối KHÔNG tự ý thay đổi thang điểm tối đa của từng tiêu chí.
2. Tuyệt đối KHÔNG chấm điểm dựa trên cảm tính hay nhận xét chung chung (như "bài làm tốt", "cần cố gắng").
3. Mọi điểm số đưa ra BẮT BUỘC phải trích dẫn minh chứng cụ thể (nguyên văn câu/cụm từ) từ bài viết của sinh viên.
4. KHÔNG cộng điểm ưu tiên chỉ vì bài viết dài; tập trung vào chất lượng lập luận và sự cô đọng.
5. Phải chỉ rõ các lỗi sai (về lập luận, cấu trúc, ngữ pháp/diễn đạt) và đề xuất cách viết lại cho hay hơn.

# THANG ĐIỂM ĐÁNH GIÁ (RUBRIC - TỔNG 10 ĐIỂM)
Bạn phải chấm điểm dựa trên đúng 5 tiêu chí sau:
1. **Đúng chủ đề (Tối đa 2.0 điểm):** Bám sát chủ đề "Vai trò của AI trong hoạt động học tập của sinh viên đại học", không lan man sang các lĩnh vực khác.
2. **Nội dung và lập luận (Tối đa 3.0 điểm):** Các luận điểm rõ ràng, logic, sâu sắc, thể hiện được góc nhìn đa chiều (lợi ích và lưu ý khi dùng AI).
3. **Ví dụ minh họa (Tối đa 2.0 điểm):** Đưa ra được các ví dụ thực tế, cụ thể (tên công cụ, tình huống học tập cụ thể) để làm sáng tỏ lập luận.
4. **Cấu trúc bài viết (Tối đa 1.5 điểm):** Đảm bảo bố cục đoạn văn hoàn chỉnh (Câu chủ đề - Các câu phát triển ý - Câu kết đoạn), độ dài chuẩn khoảng 300 từ (±10%), chuyển ý mượt mà.
5. **Ngữ pháp và diễn đạt (Tối đa 1.5 điểm):** Dùng từ chuẩn xác, văn phong học thuật phù hợp môi trường đại học, không mắc lỗi chính tả, lỗi dấu câu hay lặp từ.

# QUY TRÌNH XỬ LÝ & ĐỊNH DẠNG ĐẦU RA (OUTPUT FORMAT)
Sau khi đọc bài viết, hãy trả về kết quả theo đúng cấu trúc 3 phần dưới đây:

### 1. Bảng đối chiếu chấm điểm chi tiết (Rubric)
Trình bày dưới dạng bảng Markdown gồm 4 cột: `Tiêu chí` | `Điểm tối đa` | `Điểm đạt được` | `Minh chứng từ bài viết & Lý do chấm`. 
(Dòng cuối cùng của bảng phải tính **Tổng điểm** trên thang 10).

### 2. Nhận xét tổng quan
- **Điểm mạnh:** Nêu rõ 2-3 ưu điểm nổi bật nhất của bài viết kèm dẫn chứng.
- **Điểm yếu:** Chỉ ra các hạn chế về lập luận, ví dụ hoặc cấu trúc đoạn văn.

### 3. Chỉ rõ lỗi sai và Đề xuất cải thiện
- Liệt kê các câu văn mắc lỗi diễn đạt/ngữ pháp hoặc lập luận còn yếu -> Đưa ra phương án viết lại tối ưu hơn.
- Đưa ra 2 lời khuyên hành động giúp sinh viên nâng cao điểm số ở lần viết sau.

---
Dưới đây là bài viết của sinh viên cần chấm:
[DÁN BÀI VIẾT CỦA SINH VIÊN VÀO ĐÂY]
```

---

## 3. Bài viết mẫu của sinh viên (Khoảng 300 từ)

Để kiểm thử Prompt trên, em đã chuẩn bị một đoạn văn mẫu do sinh viên viết (có cố tình cài cắm một vài điểm mạnh và một số lỗi nhỏ về diễn đạt, ví dụ để AI phát hiện):

> **Bài làm mẫu (296 từ):**
> 
> Trong kỷ nguyên chuyển đổi số hiện nay, trí tuệ nhân tạo (AI) đang đóng một vai trò vô cùng quan trọng và trở thành người bạn đồng hành không thể thiếu trong hoạt động học tập của sinh viên đại học. Trước hết, AI giúp cá nhân hóa quá trình tự học và tiết kiệm tối đa thời gian tra cứu tài liệu. Thay vì phải mất hàng giờ đọc hàng trăm trang giáo trình dày đặc, sinh viên có thể sử dụng các công cụ như ChatGPT hay Claude để tóm tắt ý chính, giải thích các khái niệm chuyên ngành phức tạp bằng ngôn ngữ dễ hiểu. Thứ hai, AI hỗ trợ đắc lực trong việc rèn luyện kỹ năng ngoại ngữ và nghiên cứu khoa học. Chẳng hạn, sinh viên thường xuyên dùng Grammarly hoặc QuillBot để kiểm tra lỗi ngữ pháp tiếng Anh, hay dùng các công cụ AI tìm kiếm bài báo khoa học phục vụ cho khóa luận tốt nghiệp. Không những thế, AI còn đóng vai trò như một gia sư ảo 24/7, sẵn sàng giải đáp thắc mắc và gợi ý ý tưởng cho các bài tập nhóm bất cứ lúc nào. Tuy nhiên, bên cạnh những lợi ích to lớn thì việc lạm dụng AI cũng mang lại nhiều hệ lụy xấu. Nhiều bạn sinh viên hiện nay cứ có bài tập là copy paste toàn bộ lên AI để lấy đáp án mà không thèm suy nghĩ, điều này làm giảm tư duy phản biện và dẫn đến nguy cơ đạo văn rất cao trong môi trường đại học. Tóm lại, AI là một công cụ hỗ trợ học tập cực kỳ mạnh mẽ, nhưng nó chỉ thực sự phát huy giá trị khi sinh viên biết sử dụng một cách thông minh, có chọn lọc và giữ vững tính trung thực trong học thuật.

---

## 4. Kết quả AI chấm điểm và phản hồi (Output thực tế)

Dưới đây là kết quả phản hồi từ AI sau khi áp dụng Prompt và bài viết mẫu ở trên:

### 1. Bảng đối chiếu chấm điểm chi tiết (Rubric)

| Tiêu chí | Điểm tối đa | Điểm đạt được | Minh chứng từ bài viết & Lý do chấm |
| :--- | :---: | :---: | :--- |
| **Đúng chủ đề** | 2.0 | **2.0** | Toàn bộ bài viết tập trung phân tích vai trò của AI trong học tập đại học. Minh chứng ngay câu mở đầu: *"trí tuệ nhân tạo (AI) đang đóng một vai trò vô cùng quan trọng... trong hoạt động học tập của sinh viên đại học."* |
| **Nội dung và lập luận** | 3.0 | **2.5** | Nêu được 3 khía cạnh tích cực (cá nhân hóa tự học, hỗ trợ ngoại ngữ/nghiên cứu, gia sư ảo) và 1 mặt trái (lạm dụng làm giảm tư duy). Tuy nhiên, phần phân tích nguyên nhân tại sao AI giúp "cá nhân hóa" còn hơi lướt, mới chỉ dừng ở việc tóm tắt tài liệu. |
| **Ví dụ minh họa** | 2.0 | **2.0** | Đưa ra các ví dụ công cụ rất cụ thể và sát thực tế sinh viên. Minh chứng: *"sử dụng các công cụ như ChatGPT hay Claude để tóm tắt ý chính"*, *"dùng Grammarly hoặc QuillBot để kiểm tra lỗi ngữ pháp tiếng Anh"*. |
| **Cấu trúc bài viết** | 1.5 | **1.5** | Đảm bảo cấu trúc đoạn văn chuẩn (296 từ, nằm trong khoảng 300 từ ±10%). Có câu chủ đề rõ ràng, các từ nối chuyển ý mạch lạc (*"Trước hết"*, *"Thứ hai"*, *"Không những thế"*, *"Tuy nhiên"*, *"Tóm lại"*). |
| **Ngữ pháp và diễn đạt** | 1.5 | **1.0** | Cơ bản đúng chính tả, rõ ý nhưng còn dùng từ ngữ mang tính văn nói, thiếu tính học thuật ở phần thân đoạn và lặp từ *"sinh viên"* 6 lần trong một đoạn ngắn. |
| **TỔNG ĐIỂM** | **10.0** | **9.0** | **Bài viết đạt chất lượng tốt, lập luận chặt chẽ và có ví dụ thực tế.** |

### 2. Nhận xét tổng quan

* **Điểm mạnh:** 
  * Bố cục đoạn văn chuẩn xác (296 từ), sử dụng hệ thống từ nối chuyển đoạn rất mượt mà giúp người đọc dễ theo dõi mạch lập luận.
  * Ví dụ minh họa thực tế, đúng trọng tâm đối tượng sinh viên (nêu đúng tên các công cụ phổ biến như ChatGPT, Claude, Grammarly, QuillBot).
  * Có tư duy phản biện khi không chỉ ca ngợi AI mà còn chỉ ra mặt trái ở câu: *"điều này làm giảm tư duy phản biện và dẫn đến nguy cơ đạo văn rất cao"*.
* **Điểm yếu:**
  * Văn phong ở nửa sau đoạn văn hơi suồng sã (văn nói), chưa phù hợp hoàn toàn với môi trường nghị luận đại học.
  * Lập luận về tính *"cá nhân hóa"* chưa sâu (tóm tắt tài liệu mới chỉ là tiết kiệm thời gian, chưa làm rõ việc AI điều chỉnh lộ trình học theo năng lực từng người).

### 3. Chỉ rõ lỗi sai và Đề xuất cải thiện

* **Lỗi 1: Sử dụng văn nói và từ ngữ thiếu trang trọng**
  * *Câu gốc trong bài:* *"Nhiều bạn sinh viên hiện nay cứ có bài tập là **copy paste** toàn bộ lên AI để lấy đáp án mà **không thèm suy nghĩ**..."*
  * *Vấn đề:* Cụm từ *"cứ có bài tập là"*, *"copy paste"* (tiếng Anh chưa Việt hóa) và *"không thèm suy nghĩ"* mang sắc thái khẩu ngữ, thiếu tính học thuật.
  * *Đề xuất sửa:* *"Nhiều sinh viên hiện nay có xu hướng sao chép toàn bộ đề bài vào công cụ AI để lấy đáp án sẵn có thay vì tự tư duy giải quyết vấn đề..."*

* **Lỗi 2: Lặp từ vựng**
  * *Vấn đề:* Từ *"sinh viên"* xuất hiện 6 lần trong đoạn văn gây cảm giác lặp.
  * *Đề xuất sửa:* Có thể thay thế linh hoạt bằng các từ đồng nghĩa theo ngữ cảnh như *"người học"*, *"các bạn trẻ"*, *"những người nghiên cứu trẻ"*.

* **Lời khuyên để nâng điểm lên 9.5 - 10:**
  1. Bổ sung thêm 1 vế ngắn giải thích rõ AI *"cá nhân hóa"* bằng cách tạo ra bài tập/lộ trình riêng phù hợp với trình độ của từng người học.
  2. Rà soát lại toàn bài sau khi viết để thay thế các từ ngữ khẩu ngữ bằng từ vựng chuẩn văn phong nghị luận xã hội.

---

## 5. Kết luận
Qua bài thực hành, việc thiết lập các ràng buộc cứng (không đổi trọng số, bắt buộc trích dẫn nguyên văn minh chứng) trong Prompt đã giải quyết triệt để tình trạng AI chấm điểm cảm tính. Bảng đối chiếu giúp sinh viên biết chính xác mình mất điểm ở đâu và cần sửa câu chữ nào để bài viết hoàn thiện hơn.