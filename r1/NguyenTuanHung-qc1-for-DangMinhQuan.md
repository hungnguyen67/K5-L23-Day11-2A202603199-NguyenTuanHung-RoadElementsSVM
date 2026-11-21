# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Tuấn Hưng (2A202603199)  
Người kiểm (học viên): Đặng Minh Quân (2A202603171)
Ngày: 2026-11-21  
Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): `NguyenTuanHung-front.zip` và `NguyenTuanHung-fisheye.zip`, revision 1  
Số ảnh kiểm: 6 ảnh mẫu (A01, A02, A03, B01, B02, B03)  
Số nhãn đã kiểm (shape + tag): 64 mục trong 6 ảnh mẫu (40 shape + 24 tag); ngoài mẫu, hai file tổng cộng có 235 hình/tag được `road_check lint` đọc

## Tổng hợp theo mã

| Mã                                   | Loại lỗi                              | Số mục kiểm | Số lỗi | Mức          |
| ------------------------------------ | ------------------------------------- | ----------: | -----: | ------------ |
| QC1-01 tag camera                    | sai thuộc tính / bỏ sót               |           6 |      0 | nặng         |
| QC1-02 đủ L1, R1                     | bỏ sót                                |           6 |      0 | nặng         |
| QC1-03 position                      | sai thuộc tính / thừa                 |          10 |      0 | nặng         |
| QC1-04 tâm vạch, chiều, điểm dừng    | sai phạm vi / bỏ sót                  |          10 |      0 | chính        |
| QC1-05 vạch đứt, che                 | sai phạm vi / sai thuộc tính          |          10 |      0 | chính        |
| QC1-06 style, color, kind            | sai thuộc tính                        |          10 |      0 | chính        |
| QC1-07 vùng lái                      | sai phạm vi / bỏ sót / thừa           |          23 |      0 | chính        |
| QC1-08 đèn, màu                      | bỏ sót / sai phạm vi / sai thuộc tính |           4 |      0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính                        |           7 |      0 | chính        |
| QC1-10 hình in, đủ biển              | bỏ sót / sai phạm vi                  |           3 |      0 | chính        |
| QC1-11 fisheye                       | sai phạm vi / sai thuộc tính          |          18 |      0 | chính        |
| QC1-12 file                          | lỗi file                              |           2 |      0 | nhẹ / nặng   |

## Danh sách lỗi (mỗi lỗi một dòng)

| #   | Mã  | Ảnh | Nhãn (label, id)   | Mức            | Mô tả ngắn                                                                                                                   |
| --- | --- | --- | ------------------ | -------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1   | —   | A05 | lane, L1; lane, R1 | Không tính mức | Ảnh không có vạch ứng với `position = L1` và `R1`; không gán thêm nhãn. Đây là ngoại lệ được phép, không tính là lỗi bỏ sót. |
| 2   | —   | A06 | lane, R1           | Không tính mức | Ảnh không có vạch ứng với `position = R1`; không gán thêm nhãn. Đây là ngoại lệ được phép, không tính là lỗi bỏ sót.         |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead                                                                                                            | Lời đáp (nếu có)                                                                                 |
| --- | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| A05 | Ảnh có vạch tương ứng với `lane.position = L1` và `R1` không; liệu việc không gán hai vạch này có được xem là bỏ sót không? | Không có vạch tương ứng L1/R1 trên ảnh; không gán nhãn là đúng quy tắc và không tính lỗi QC1-02. |
| A06 | Ảnh có vạch tương ứng với `lane.position = R1` không; liệu việc không gán R1 có được xem là bỏ sót không?                   | Không có vạch tương ứng R1 trên ảnh; không gán nhãn là đúng quy tắc và không tính lỗi QC1-02.    |

## Quyết định

Lỗi nặng đã xác nhận: **0**  
Lỗi chính: **0** / **0 nhãn thủ công = 0 %**  
Lỗi nhẹ: **0**  
Ca chờ lead: **0**  
Quyết định (Release / Hold / Rework): **Release**  
Lý do (theo luật của phiếu): Hai ca thiếu L1/R1 ở A05 và A06 là do ảnh không có vạch tương ứng, nên được ngoại lệ và không tính là lỗi. Không có lỗi nặng, không có lỗi chính vượt 5 %.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
