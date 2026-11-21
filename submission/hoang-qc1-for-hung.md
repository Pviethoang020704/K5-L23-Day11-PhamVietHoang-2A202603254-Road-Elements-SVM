# PHIẾU QC 1 — ROAD V1.0

**Lô được kiểm (học viên):** Nguyễn Văn Hùng - 2A202603295  
**Người kiểm (học viên):** Phạm Việt Hoàng - 2A202603254  
**Ngày:** 20/11/2026  
**Phiên bản guideline:** Road v1.0   
**Số ảnh kiểm:** 6 (A01–A06)  
**Số nhãn đã kiểm (shape + tag):** 120

## 1. Danh sách ảnh cần kiểm

| Ảnh | Số nhãn | Lỗi chính | Lỗi nhẹ | Ghi chú |
|---|---:|---:|---:|---|
| A01 | 18 | 1 | 0 | Cần điều chỉnh điểm kết thúc polyline |
| A02 | 21 | 1 | 0 | Cần điều chỉnh cách biểu diễn vạch đứt |
| A03 | 19 | 1 | 0 | Cần kiểm tra thuộc tính màu vạch |
| A04 | 23 | 1 | 0 | Cần điều chỉnh phạm vi vùng lái |
| A05 | 20 | 0 | 1 | Cần rà soát thông tin file |
| A06 | 19 | 0 | 1 | Cần rà soát thông tin file |
| **Tổng** | **120** | **4** | **2** | |

## 2. Tổng hợp theo mã

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
|---|---|---:|---:|---|
| QC1-01 tag camera | Sai thuộc tính / bỏ sót | 6 | 0 | Nặng |
| QC1-02 đủ L1, R1 | Bỏ sót | 14 | 0 | Nặng |
| QC1-03 position | Sai thuộc tính / thừa | 14 | 0 | Nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | Sai phạm vi / bỏ sót | 14 | 1 | Chính |
| QC1-05 vạch đứt, che | Sai phạm vi / sai thuộc tính | 10 | 1 | Chính |
| QC1-06 style, color, kind | Sai thuộc tính | 14 | 1 | Chính |
| QC1-07 vùng lái | Sai phạm vi / bỏ sót / thừa | 12 | 1 | Chính |
| QC1-08 đèn, màu | Bỏ sót / sai phạm vi / sai thuộc tính | 8 | 0 | Nặng / Chính |
| QC1-09 facing, type, group, biển phụ | Sai thuộc tính | 8 | 0 | Chính |
| QC1-10 hình in, đủ biển | Bỏ sót / sai phạm vi | 8 | 0 | Chính |
| QC1-11 fisheye | Không áp dụng cho Front | N/A | N/A | Chính |
| QC1-12 file | Lỗi file | 12 | 2 | Nhẹ / Nặng |

## 3. Danh sách lỗi

| # | Mã | Ảnh | Nhãn (label, ID) | Mức | Mô tả ngắn |
|---|---|---|---|---|---|
| 1 | QC1-04 | A01 | lane, ID chưa xác nhận | Chính | Polyline kết thúc trước điểm cuối của vạch sơn, chưa bao phủ hết đoạn vạch nhìn thấy |
| 2 | QC1-05 | A02 | lane, ID chưa xác nhận | Chính | Vạch đứt liên tục được biểu diễn bằng hai polyline riêng biệt |
| 3 | QC1-06 | A03 | lane, ID chưa xác nhận | Chính | Thuộc tính màu của vạch vàng được đặt thành `white` |
| 4 | QC1-07 | A04 | drivable, ID chưa xác nhận | Chính | Polygon bao gồm một phần lề đường nằm ngoài khu vực xe có thể di chuyển |
| 5 | QC1-12 | A05 | Thông tin file | Nhẹ | Thông tin mô tả file cần được chuẩn hóa |
| 6 | QC1-12 | A06 | Thông tin file | Nhẹ | Thông tin mô tả file cần được chuẩn hóa |

### Đề xuất chỉnh sửa

- **A01:** Điều chỉnh điểm cuối polyline để bám sát toàn bộ vạch sơn quan sát được.
- **A02:** Gộp các đoạn thuộc cùng một vạch đứt thành một polyline liên tục.
- **A03:** Kiểm tra và điều chỉnh thuộc tính `color` theo màu vạch thực tế.
- **A04:** Thu hẹp Polygon `drivable`, loại bỏ phần lề đường không thuộc vùng xe được phép di chuyển.
- **A05–A06:** Rà soát thông tin file và chuẩn hóa theo yêu cầu xuất dữ liệu.

## 4. Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp |
|---|---|---|
| — | Không có nội dung cần phân xử trong bảng mẫu | — |

## 5. Quyết định

**Lỗi nặng:** 0  
**Lỗi chính:** 4  
**Tổng số nhãn kiểm:** 120  
**Tỷ lệ lỗi chính:** 3,33%  
**Lỗi nhẹ:** 2  
**Ca chờ lead:** 0  

**Quyết định theo số liệu trong bảng: RELEASE**

**Lý do:**

Không có lỗi thuộc mức nặng. Tỷ lệ lỗi chính đạt 3,33%, thấp hơn ngưỡng 5% theo quy tắc QC1. Không có trường hợp cần chuyển lead phân xử.

Các vấn đề được liệt kê tập trung vào độ chính xác của polyline, thuộc tính màu và ranh giới Polygon. Những nội dung này cần được rà soát và điều chỉnh để bảo đảm tính nhất quán của bộ dữ liệu.

**Quy tắc áp dụng:**

- Có ít nhất một lỗi nặng: Rework.
- Tỷ lệ lỗi chính vượt 5% tổng số nhãn kiểm: Rework.
- Có ca chưa được giải đáp ảnh hưởng kết luận: Hold.
- Không thuộc các trường hợp trên: Release.

---

**Người lập phiếu:** Phạm Việt Hoàng - 2A202603254  
**Ngày lập:** 20/11/2026