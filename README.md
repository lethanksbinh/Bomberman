# Bài tập lớn OOP - Bomberman Game

Bài tập lớn môn Lập trình Hướng đối tượng - INT2204 22
Người thực hiện: 
- Lê Thanh Bình - 21020537
- Nguyễn Huy Thái - 21020035

## Mô tả về các đối tượng trong trò chơi

- ![](readme/player.png) *Bomber* là nhân vật chính của trò chơi. Bomber có thể di chuyển theo 4 hướng trái/phải/lên/xuống theo sự điều khiển của người chơi. 

- ![](readme/bomb.png) *Bomb* là đối tượng mà Bomber sẽ đặt. Khi đã được đặt, Bomber không thể di chuyển vào vị trí Bomb. Tuy nhiên ngay khi Bomber vừa đặt và kích hoạt Bomb tại ví trí của mình, Bomber có một lần được đi từ vị trí đặt Bomb ra vị trí bên cạnh. Sau khi kích hoạt 2s, Bomb sẽ tự nổ. Bomb cũng có thể được kích hoạt bằng flame của bomb khác.

- ![](readme/grass.png) *Grass* là đối tượng mà Bomber và Enemy có thể di chuyển xuyên qua, và cho phép đặt Bomb lên vị trí của nó.

- ![](readme/wall.png) *Wall* là đối tượng cố định, không thể phá hủy bằng Bomb cũng như không thể đặt Bomb lên được, Bomber không thể di chuyển vào đối tượng này

- ![](readme/brick.png) *Brick* là đối tượng không cho phép đặt Bomb lên nhưng có thể bị phá hủy bởi Bomb được đặt gần đó. Bomber không thể di chuyển vào vị trí Brick khi nó chưa bị phá hủy.

- ![](readme/portal.png) *Portal* là đối tượng được giấu phía sau một đối tượng Brick. Khi Brick đó bị phá hủy, Portal sẽ hiện ra và nếu tất cả Enemy đã bị tiêu diệt thì người chơi có thể qua Level khác bằng cách di chuyển vào vị trí của Portal.

*Item* cũng được giấu phía sau Brick và chỉ hiện ra khi Brick bị phá hủy. Bomber có thể sử dụng Item bằng cách di chuyển vào vị trí của Item. Thông tin về chức năng của các Item được liệt kê như sau:

- ![](readme/powerup_speed.png) *SpeedItem* Item này sẽ giúp Bomber được tăng tốc độ di chuyển.

- ![](readme/powerup_bombs.png) *BombItem* Item này giúp tăng số lượng Bomb có thể đặt thêm một.

- ![](readme/powerup_flames.png) *FlameItem* Item này giúp tăng phạm vi ảnh hưởng của Bomb khi nổ.

*Enemy* là các đối tượng mà Bomber phải tiêu diệt hết để có thể qua Level. Enemy có thể di chuyển ngẫu nhiên hoặc tự đuổi theo Bomber tùy theo loại Enemy. Các loại Enemy sẽ được mô tả cụ thể sau đây:

- ![](readme/ballom.png) *Ballom* là Enemy đơn giản nhất, di chuyển ngẫu nhiên với tốc độ chậm.

- ![](readme/oneal.png) *Oneal* biết đuổi Bomber khi lại gần, có tốc độ di chuyển tăng trong khi đuổi Bomber.

- ![](readme/pass.png) *Pass* biết đuổi Bomber với phạm vi toàn bản đồ, sử dụng thuật toán A*.

- ![](readme/dahl.png) *Dahl* di chuyển ngẫu nhiên và biết né bomb.

- ![](readme/doria.png) *Doria* biết đuổi Bomber khi lại gần, có tốc độ di chuyển tăng và có thể di chuyển xuyên Brick.

## Singleplayer
- Trong một màn chơi, Bomber sẽ được người chơi di chuyển, đặt và kích hoạt Bomb với mục tiêu chính là tiêu diệt tất cả Enemy và tìm ra vị trí Portal để có thể qua màn mới.
- Bomber sẽ bị giết khi va chạm với Enemy hoặc thuộc phạm vi Bomb nổ. Lúc đấy trò chơi kết thúc.
- Enemy bị tiêu diệt khi thuộc phạm vi Bomb nổ.
- Khi Bomb nổ, một Flame trung tâm tại vị trí Bomb nổ và các Flame tại bốn vị trí ô đơn vị xung quanh vị trí của Bomb xuất hiện theo bốn hướng trên/dưới/trái/phải. 
- Khi các Flame xuất hiện, nếu có một đối tượng thuộc loại Brick/Wall nằm trên vị trí một trong các Flame thì Flame sẽ bị chặn lại đến vị trí đó.

## Multiplayer
- Solo 1 vs 1.
- Kết nối qua mạng LAN (cùng 1 wifi).
- Không giới hạn thời gian, số lần thắng thua.
- Có thêm 2 loại bomb mới:
  - Lazerbomb (bắn thẳng, xuyên qua tường)
  - Lightbomb (có thể được di chuyển sau khi đặt)
- Sau khi chết, người chơi quay lại điểm xuất phát.

## BombOverloading
- Khi 2 quả bomb nổ gần nhau, chúng sẽ tăng cường phạm vi nổ