# ThucTap
•	Viết API Thêm sửa xóa, tìm kiếm danh sách không có quan hệ:
+	Tỉnh, Huyện ,Xã, Văn bằng chứng chỉ (có thời gian hiệu lực từ ngày bao nhiêu đến ngày bao nhiêu)
•	Viết API Thêm sửa xóa, tìm kiếm danh sách Tỉnh, Huyện có quan hệ Tỉnh 1 - n với Huyện
+	Thêm Huyện xác định luôn thuộc Tỉnh nào
+	Xoá Tỉnh thì xoá toàn bộ Huyện thuộc Tỉnh
+	Tìm kiếm toàn bộ Huyện dựa theo id của Tỉnh
+	Thêm Tỉnh và Huyện cùng 1 lúc - Gửi thông tin Tỉnh và 1 loạt list Huyên -> Lưu đồng thời xuống database
+	Sửa Tỉnh và Huyện cùng 1 lúc - Gửi thông tin Tỉnh và 1 loạt list Huyên (Các huyện đều đã tồn tại trong database, sửa theo thông tin truyền vào)

•	Viết API Thêm sửa xóa, tìm kiếm danh sách Tỉnh, Huyện có quan hệ Huyện có quan hệ 1 - n với Xã
+	Thêm Xã xác định luôn thuộc Huyện nào
+	Xoá Huyện thì xoá toàn bộ Xã thuộc Huyện
+	Tìm kiếm toàn bộ xã dựa theo id của Huyện
+	Thêm Huyện và Xã cùng 1 lúc - Gửi thông tin Huyện và 1 loạt list xã -> Lưu đồng thời xuống database
+	Sửa Huyện và Xã cùng 1 lúc - Gửi thông tin Huyện và 1 loạt list Xã (Các huyện đều đã tồn tại trong database, sửa theo thông tin truyền vào)
+	 Thêm Tỉnh, Huyện và Xã đồng thời từ thông tin được gửi lên
+	 Xoá Tỉnh thì Huyện và Xã thuộc tỉnh đều bị xoá theo.

•	Xử lí logic cho Api
Validate trên server các thông tin đầu vào đối với Employee:
- Code không được trùng, không có dấu cách, dài tối thiểu 6 ký tự tối đa 10 ký tự, bắt buộc
- Tên bắt buộc nhập 
- Email đúng định dạng, bắt buộc
- Số điện thoại chỉ gồm số không dài quá 11 ký tự, bắt buộc
- Tuổi không được âm, 
- Các logic tiếp theo sẽ tự nghĩ thêm. 
Thông tin trả về sẽ gồm các thông tin:
- data: Dữ liệu chính trả về
- errorCode: Mã code lỗi (nếu có)
- errorMessage: Thông tin cụ thể của lỗi (nếu có)

•	Employee sẽ có thêm 3 trường: Tỉnh, Huyện, Xã
 - Thêm mới employee phải có cả 3 trường này
 - Sửa: Nếu gửi thông tin sửa của cả 3 trường mới sửa, không thì bỏ qua

•	Validate khi thêm và sửa 3 trường Tỉnh Huyện Xã của employee
- Xã phải thuộc Huyện
- Huyện phải thuộc Tỉnh

Nghiệp vụ:
 - Một Employee sẽ có nhiều văn bằng
 - Mỗi văn bằng sẽ do một tỉnh cấp
  
Yêu cầu:
 - Thêm văn bằng cho nhân viên - văn bằng sẽ do 1 tỉnh cụ thể cung cấp (1 List)
 - Nếu Employee đã có  văn bằng A của tỉnh X cung cấp thì không được thêm mới văn bằng A được tỉnh X nếu văn bằng đó còn hiệu lực.
 - Employee không được có quá 3 văn bằng cùng loại còn hiệu lực (Bất kể tỉnh nào cung cấp)
- Import excel thông tin nhiều Employee (Có Tỉnh, Huyện, Xã - Không có văn bằng)
- Validate thông tin được import. Nếu lỗi bất kì dòng nào thì trả về lỗi (có kèm theo dòng thứ bao nhiêu lỗi) và không lưu vào database.

•	Thống kê danh sách các Employee có số lượng văn bằng >2

•	Api  Tổng số lượng employee Group by Tỉnh

•	Api  tìm kiếm theo tỉnh

•	Api Tổng số lượng employee theo từng Huyện nếu tìm kiếm theo 1 tỉnh

•	Api  % số lượng employee có 1 văn bằng, 2 văn bằng và  >2 văn bằng

•	Api Tìm kiếm theo tỉnh , tính % số lượng employee có 1 văn bằng, 2 văn bằng và  >2 văn bằng đối với tỉnh đang tìm kiếm

•	Api tổng số lượng employee thêm mới Group by created date (mặc định  30 ngày gần nhất)

•	Api Tìm kiếm theo khoảng thời gian

•	 Api Tổng số lượng employee có 1 văn bằng, 2 văn bằng và  >2 văn bằng

•	group by tỉnh

•	Tìm kiếm theo tỉnh 

•	Tìm kiếm tỉnh, group theo huyện
