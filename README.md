# QuanLyRapPhim
C# - Lập trình winform

# Tài khoản: 
- NguyenHongLiem pass admin
- VuThiHien pass admin
- TranHuynhNhu pass admin
- Mọi NV đều có pass là 1

# USECASE VÀ ACTIVITY DIAGRAM XEM Ở FILE: Hệ thống quản lý rạp chiếu phim.mdj

# HƯỚNG DẪN - TUTOR:

Quản lý rạp phim 
-> connect sql server database
-> chạy script database


I. Trong phần mềm bấm setting để connect vào server name (trên máy local), giữ nguyên database name -> bấm lưu và kết nối
-> kết nối thành công

II. Tài khoản mặc định của admin: tên và pass đều là admin -> login

1. form quản lý: các tab
- tạo xuất chiếu: bấm vào phim -> tạo mới hoặc chọn có sẵn, nhập bằng tay
				trong database tự liên kết mục phim và thể loại -> nhưng trên form của khách hàng thì ko hiển thị
				thể loại là checkbox, ngày khởi chiếu và ngày kết thúc là daypickedlist
				-> thêm phim bắt buộc phải có hình ảnh
				-> nếu đầy đủ thì hiển thị thông báo
- Định dạng: table liên kết phim với loại màng hình	-> phải chọn định dạng	
- lịch chiếu: tạo và hiển thị tương tứng với loại màn hình trong định dạng	
				giờ chiếu phải nằm trong khoảng ngày khởi chiếu và ngày kết thúc của lúc đầu khởi tạo
					-> nếu ko đúng sẽ báo trigger
				format thời gian: tùy thuộc vào format máy/laptop
- sau khi tạo lịch chiếu xong phải sang tạo vé để bán
	+ có thể tạo tự động, xóa...
	status: trạng thái (được bán: 1, chưa được bán: 0) -> bán thì giá vé sẽ được truyền vào price
2. form bán vé	
- chọn thời gian lịch chiếu
- click vào listview -> xuất hiện ra form màn ảnh
- chọn loại vé thì có thể giảm giá, sau khi chọn ghế thì có thể loại ghế, 
		sau đó chọn tiếp và thao tác loại vé liên tục như v
- chọn lại ghế thì hủy ko chọn nữa	
- nếu là khách hàng thành viên thì cung cấp mã 
- sau khi xác nhận thì sẽ hiển thị ra thông tin của khác hàng 
	+ điểm cộng thêm: mỗi lần mua 1 vé thì + 1 điểm, 20 điểm thì đổi được 1 vé miễn phí
	+ bấm thanh toánh thì có messagebox xác nhận -> confirm -> thành công
		-> sau khi mua thành công thì chuyển ghế sang màu đỏ -> đồng thời lưu về database 
				-> hiển thị ở phần quản lý -> mục doanh thu (theo tháng) -> hiển thị -> 
							các báo cáo thì xuất hiện để quản lý in ra
				
III. 11 bảng:
	- Nhân Viên 
	- Tài Khoản
	- Khách hàng
	- Vé
	- Lịch chiếu
	- Định dạng phim
	- Phim
	- Phòng chiếu
	- Loài màn hình
	- Phân loại phim
	- Thể loại

IV. 18 Form admin: 
	- 1 form điều hướng admin (Admin New Design)
	- 8 form: + 1. dock data dữ liệu (data UC: user control)
	 		  + 7. Loại màn hình, phòng chiếu, thể loại, phim, định dạng phim, lịch chiếu, vé (DataUserControl)
	- 1 form thống kê báo cáo (ravenueUC)
	- 1 form nhân viên	(staffUC)
	- 1 form khách hàng	(customerUC)
	- 1 form tài khoản	(accountUC)
	- 1 form xuất báo cáo (Report)
	- 4 Form chung: 
		+ 1 form đăng nhập (Login)
		+ 1 form kết nối dữ liệu database (Connect Data)
		+ 1 form dashboard để điều hướng (Dashboard)
		+ 1 form đổi mật khẩu (accountSetting)
		+ (Và các form của nhân viên)

V. 3 Form nhân viên:	
	- Form bán vé (seller)
	- Form rạp phim (theatre)
	- Form nhập thông tin khách hàng thành viên (customer)
	
	
	





				
				


