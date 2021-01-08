#1
- Tác nhân là 1 công cụ lập kế hoạch ngoại ngoại tuyến, không phải tác nhân học tăng cường
  -> vì vậy tùy chọn đào tạo có liên quan là số lần lặp lại giá trị mà nó sẽ chạy (tùy chọn -i) trong giai đoạn lập kế hoạch ban đầu của nó. ValueIterationAgent lấy MDP khi xây dựng và chạy lặp giá trị cho số lần lặp được chỉ định trước khi hàm tạo trả về.

- Phép lặp giá trị tính toán các ước lượng k-bước của các giá trị tối ưu Vk, triển khai các phương pháp sau cho ValueIterationAgent bằng cách sử dụng Vk.

`computeActionFromValues`(trạng thái)
tính toán hành động tốt nhất theo hàm giá trị được cung cấp bởi giá trị tự.
`computeQValueFromValues` ​​(trạng thái, hành động) trả về giá trị Q của cặp (trạng thái, hành động) được cung cấp bởi hàm giá trị do self.values ​​cung cấp.

#2
- BridgeGrid là một bản đồ dạng lưới với trạng thái đầu cuối có phần thưởng thấp và trạng thái cuối có phần thưởng cao được ngăn cách bởi một "cây cầu" hẹp, ở hai bên là hố sâu có phần thưởng âm cao. Tác nhân bắt đầu gần trạng thái phần thưởng thấp. Với chiết khấu mặc định là 0,9 và độ ồn mặc định là 0,2, chính sách tối ưu không qua cầu. Chỉ thay đổi MỘT trong các thông số chiết khấu và tiếng ồn để chính sách tối ưu khiến đại lý nỗ lực qua cầu. Đặt câu trả lời của bạn trong question2 () of analysis.py. (Tiếng ồn đề cập đến tần suất một tác nhân kết thúc ở trạng thái kế thừa không mong muốn khi họ thực hiện một hành động.) Giá trị mặc định tương ứng với

#3 
- Cho một bản đồ cho trước, có điểm trả giá
- Trong câu hỏi này, bạn sẽ chọn cài đặt của các tham số chiết khấu, độ ồn và phần thưởng sống cho MDP này để tạo ra các chính sách tối ưu của một số loại khác nhau. Việc bạn cài đặt các giá trị tham số cho từng phần phải có thuộc tính mà nếu tác nhân của bạn tuân theo chính sách tối ưu của nó mà không bị nhiễu, nó sẽ thể hiện hành vi đã cho. Nếu một hành vi cụ thể không đạt được đối với bất kỳ cài đặt thông số nào, hãy khẳng định rằng chính sách là không thể bằng cách trả về chuỗi 'KHÔNG CÓ THỂ'.

* Dưới đây là các loại chính sách tối ưu mà bạn nên cố gắng tạo ra:

- Thích lối ra gần (+1), mạo hiểm với vách đá (-10)
- Thích lối ra gần (+1), nhưng tránh vách đá (-10)
- Thích lối ra xa (+10), mạo hiểm với vách đá (-10)
- Thích lối ra xa (+10), tránh vách đá (-10)
- Tránh cả lối ra và vách đá (vì vậy một tập phim sẽ không bao giờ kết thúc)

#4

- Viết Q-learning agent, nó thực hiện rất ít trong việc xây dựng, mà thay vào đó học bằng cách thử và sai từ các tương tác với môi trường thông qua phương pháp cập nhật (trạng thái, hành động, trạng thái tiếp theo, phần thưởng). Sơ lược về Q-learning được chỉ định trong QLearningAgent trong qlearningAgents.py và bạn có thể chọn nó bằng tùy chọn '-a q'. Đối với câu hỏi này, bạn phải triển khai các phương thức `update`, `computeValueFromQValues`, `getQValue` và `computeActionFromQValues`.

Với bản cập nhật Q-learning được cung cấp, bạn có thể xem Q-learningner của mình học dưới sự điều khiển thủ công, sử dụng bàn phím:

#5
- Hoàn thành tác nhân học hỏi Q của bạn bằng cách triển khai lựa chọn hành động tham lam epsilon trong `getAction`, có nghĩa là nó chọn các hành động ngẫu nhiên trong một phần thời gian epsilon và theo cách khác, giá trị Q tốt nhất hiện tại của nó. Lưu ý rằng việc chọn một hành động ngẫu nhiên có thể dẫn đến việc chọn một hành động tốt nhất - nghĩa là bạn không nên chọn một hành động tối ưu phụ ngẫu nhiên mà nên chọn bất kỳ hành động pháp lý ngẫu nhiên nào.

#6
- Đầu tiên, đào tạo một Q-learning hoàn toàn ngẫu nhiên với tốc độ học mặc định trên BridgeGrid không ồn ào trong 50 tập và quan sát xem nó có tìm ra chính sách tối ưu hay không.
