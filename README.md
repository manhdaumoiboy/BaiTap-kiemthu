# BaiTap-kiemthu nop 
bai tap Can't Unsee 




<img width="1919" height="1078" alt="Screenshot 2026-01-05 144247" src="https://github.com/user-attachments/assets/d3a210be-8bb5-4cfe-97d7-d2559c43d5a6" />




Bài tập thực hành kiểm thử với JUnit Chủ đề: Phân tích dữ liệu điểm số học sinh Mục tiêu học tập: Biết cách viết kiểm thử tự động bằng JUnit Biết cách khai thác AI tạo sinh để hỗ trợ lập trình

Mô tả yêu cầu chức năng Chương trình Java có lớp StudentAnalyzer chứa 2 phương thức:
1.1. countExcellentStudents(List scores) Mục đích: Phân tích điểm số và trả về số lượng học sinh đạt loại Giỏi (>= 8.0) Quy tắc xử lý: Bỏ qua điểm âm hoặc lớn hơn 10 (coi là dữ liệu sai) Nếu danh sách rỗng hoặc null, trả về 0 Chỉ đếm các điểm hợp lệ (từ 0 đến 10) và >= 8.0 1.2. calculateValidAverage(List scores) Mục đích: Tính điểm trung bình của các điểm hợp lệ (từ 0 đến 10) Quy tắc xử lý: Bỏ qua điểm âm hoặc lớn hơn 10 Nếu danh sách rỗng hoặc null, trả về 0.0 Nếu không có điểm hợp lệ nào, trả về 0.0 Chỉ tính trung bình của các điểm hợp lệ Yêu cầu kỹ thuật: Điều kiện 1: Nếu điểm nhỏ hơn 0 hoặc lớn hơn 10 thì bỏ qua (validate) Điều kiện 2: Nếu danh sách rỗng thì trả về kết quả mặc định (0) Vòng lặp 1: Duyệt qua danh sách điểm để lọc học sinh giỏi Vòng lặp 2: Duyệt qua danh sách để tính trung bình hợp lệ 2. Cấu trúc dự án unit-test/ ├── pom.xml # File cấu hình Maven ├── README.md # Tài liệu hướng dẫn ├── src/ │ └── main/ │ └── java/ │ └── StudentAnalyzer.java # Lớp chính cần implement └── src/ └── test/ └── java/ └── StudentAnalyzerTest.java # Các test case JUnit 3. Cách chạy chương trình Yêu cầu hệ thống: Java JDK 11 hoặc cao hơn Maven 3.6+ hoặc có thể sử dụng Maven Wrapper Cài đặt và chạy: Bước 1: Cài đặt dependencies cd unit-test mvn clean install Bước 2: Chạy các test case mvn test Hoặc chạy test cụ thể:

mvn test -Dtest=StudentAnalyzerTest Bước 3: Xem kết quả Sau khi chạy mvn test, kết quả sẽ hiển thị trong terminal. Tất cả các test case sẽ được thực thi và báo cáo kết quả.

Cách chạy từ IDE (IntelliJ IDEA / Eclipse): Mở project trong IDE Chuột phải vào file StudentAnalyzerTest.java Chọn "Run All Tests" hoặc "Run StudentAnalyzerTest" Xem kết quả trong cửa sổ Test Results 4. Các test case đã được implement Test cho countExcellentStudents(): testCountExcellentStudents_NormalCase_MixedValidInvalid:

Test với danh sách có điểm hợp lệ và không hợp lệ testCountExcellentStudents_NormalCase_AllValid:

Test với danh sách toàn bộ điểm hợp lệ testCountExcellentStudents_EdgeCase_EmptyList:

Test với danh sách trống testCountExcellentStudents_EdgeCase_NullList:

Test với danh sách null testCountExcellentStudents_EdgeCase_BoundaryValues:
Test với giá trị biên (0, 10) testCountExcellentStudents_EdgeCase_ExactlyEight:

Test với điểm chính xác 8.0 testCountExcellentStudents_ExceptionCase_InvalidScores:

Test với tất cả điểm không hợp lệ testCountExcellentStudents_ExceptionCase_MixedInvalid:

Test kết hợp điểm hợp lệ và không hợp lệ Test cho calculateValidAverage(): testCalculateValidAverage_NormalCase_MixedValidInvalid:

Test với danh sách có điểm hợp lệ và không hợp lệ testCalculateValidAverage_NormalCase_AllValid:

Test với danh sách toàn bộ điểm hợp lệ testCalculateValidAverage_EdgeCase_EmptyList:

Test với danh sách trống testCalculateValidAverage_EdgeCase_NullList:

Test với danh sách null testCalculateValidAverage_EdgeCase_BoundaryValues:

Test với giá trị biên (0, 10) testCalculateValidAverage_ExceptionCase_AllInvalid:

Test với tất cả điểm không hợp lệ testCalculateValidAverage_ExceptionCase_MixedInvalid:

Test kết hợp điểm hợp lệ và không hợp lệ testCalculateValidAverage_SingleValue:

Test với một giá trị duy nhất testCalculateValidAverage_WithNullValues:

Test với giá trị null trong danh sách 5. Ví dụ sử dụng import java.util.Arrays; import java.util.List;

public class Example { public static void main(String[] args) { StudentAnalyzer analyzer = new StudentAnalyzer();

    // Ví dụ 1: Đếm học sinh giỏi
    List<Double> scores1 = Arrays.asList(9.0, 8.5, 7.0, 11.0, -1.0);
    int excellentCount = analyzer.countExcellentStudents(scores1);
    System.out.println("Số học sinh giỏi: " + excellentCount); // Kết quả: 2
    
    // Ví dụ 2: Tính điểm trung bình
    List<Double> scores2 = Arrays.asList(9.0, 8.5, 7.0, 11.0, -1.0);
    double average = analyzer.calculateValidAverage(scores2);
    System.out.println("Điểm trung bình: " + average); // Kết quả: 8.17
}
} 6. Kết quả kiểm thử Sau khi chạy mvn test, tất cả các test case sẽ được thực thi và báo cáo kết quả. Các test case đã được thiết kế để bao phủ:

Trường hợp bình thường (normal cases) Trường hợp biên (edge cases) Trường hợp ngoại lệ (exception cases) 7. Lưu ý Điểm hợp lệ: từ 0.0 đến 10.0 (bao gồm cả hai giá trị) Điểm không hợp lệ: < 0.0 hoặc > 10.0 sẽ bị bỏ qua Giá trị null trong danh sách sẽ bị bỏ qua Học sinh giỏi: điểm >= 8.0
