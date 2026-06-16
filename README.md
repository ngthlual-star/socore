# SoCore

**SoCore** là plugin Minecraft all-in-one dành cho máy chủ Việt Nam, tập trung vào việc tùy biến giao diện hiển thị của server: **MOTD**, **TAB**, **NameTags**, **Scoreboard**, **BossBar**, **Welcome Title**, **ActionBar**, **Broadcast**, **Animation**, **Placeholder** và API cho developer.

Plugin được phát triển bởi **Socust Network** với mục tiêu tạo một hệ thống cấu hình thân thiện, dễ chỉnh sửa, hỗ trợ tiếng Việt trong chú thích config và hoạt động tốt cho cả server nhỏ lẫn network lớn.

---

## Thông tin plugin

| Thông tin | Giá trị |
|---|---|
| Tên plugin | SoCore |
| Phiên bản | 1.0.0-BETA |
| Tác giả | Socust Network |
| Nền tảng | Bukkit / Spigot / Paper, BungeeCord, Velocity |
| Phiên bản hỗ trợ | Minecraft 1.8 → 1.26.x |
| Trạng thái | Đang phát triển, có thể còn lỗi |

---

## Tính năng chính

### MOTD

- MOTD ngẫu nhiên theo danh sách.
- Hỗ trợ 2 dòng MOTD.
- Hỗ trợ màu `&`, RGB `&#RRGGBB`, Gradient `<#RRGGBB>text</#RRGGBB>`.
- Hỗ trợ Animation trong MOTD bằng `%animation_name%`.
- Fake players:
  - Số lượng người chơi giả cố định.
  - Hoặc tự động cộng thêm số slot tối đa theo online hiện tại.
- Random server icon từ thư mục `plugins/SoCore/icons/`.
- Tự động xử lý màu phù hợp với client cũ.

### TAB Header / Footer

- Tùy chỉnh Header/Footer nhiều dòng.
- Hỗ trợ PlaceholderAPI.
- Hỗ trợ Animation động.
- Update interval riêng trong config.
- Có thể hiển thị online, max players, tên server, thông tin Discord, website, trạng thái network.

### NameTags

- Prefix/Suffix theo nhóm quyền.
- Hỗ trợ nhóm mặc định, admin, mod, vip hoặc nhóm tùy chỉnh.
- Collision rule: bật/tắt va chạm người chơi.
- Anti-override: hạn chế plugin khác ghi đè NameTag.
- Ẩn NameTag khi người chơi tàng hình.
- Phù hợp cho server survival, lobby, minigame, network.

### Sorting TAB

- Sắp xếp người chơi trong TAB theo:
  - Nhóm quyền.
  - Permission node.
  - Bảng chữ cái.
  - Placeholder dạng số.
  - Quy tắc tùy chỉnh.
- Có tùy chọn phân biệt chữ hoa/thường.

### Scoreboard

- Scoreboard bên phải màn hình.
- Hỗ trợ tối đa 15 dòng.
- Hỗ trợ PlaceholderAPI.
- Hỗ trợ Animation ở title và từng dòng.
- Tự động kiểm tra xung đột cơ bản với scoreboard khác.
- Lưu trạng thái bật/tắt của người chơi.
- Update interval riêng.

### BossBar

- Nhiều BossBar trong danh sách.
- Tự động chuyển BossBar theo thời gian.
- Mỗi BossBar có thể cấu hình riêng:
  - `text`
  - `color`
  - `style`
  - `progress`
  - `duration`
  - `progress-mode`
- Các kiểu progress:
  - `DECREASE`: giảm đều từ progress về 0.
  - `SURGE`: giảm nhanh lúc đầu, chậm dần về cuối.
  - `INCREASE`: tăng dần từ 0 lên progress.
  - `STATIC`: giữ nguyên progress.
- Hỗ trợ Animation và Placeholder trong text.
- Lưu trạng thái bật/tắt của từng người chơi.

### Welcome Title / ActionBar

- Gửi Title/Subtitle khi người chơi tham gia.
- Gửi ActionBar chào mừng.
- Phân biệt:
  - Người chơi đã từng tham gia.
  - Người chơi lần đầu tham gia.
- Cấu hình riêng `fade-in`, `stay`, `fade-out`.
- Hỗ trợ Animation, RGB, Gradient, PlaceholderAPI.

### Broadcast / Announcements

- Hệ thống thông báo tự động.
- Mỗi thông báo có thể bật/tắt riêng.
- Mỗi thông báo có interval riêng.
- Hỗ trợ các loại:
  - `CHAT`
  - `ACTIONBAR`
  - `TITLE`
- Hỗ trợ chuỗi thông báo:
  - Thông báo 1
  - Sau X tick
  - Thông báo 2
  - Sau X tick
  - Thông báo tiếp theo
- Có thể dùng để tạo tutorial, hướng dẫn server, quảng bá Discord, nhắc vote, nhắc donate.
- Hỗ trợ Animation và PlaceholderAPI.

### BelowName

- Hiển thị thông tin dưới tên người chơi.
- Có thể hiển thị máu, điểm, level hoặc placeholder khác.
- Hỗ trợ text tùy chỉnh.

### Layout TAB

- Định hướng hỗ trợ bố cục 80 ô trong TAB.
- Có thể mở rộng cho fake slots, static slots, group slots.
- Hiện đang là module nền để phát triển tiếp NMS/packet.

### Animation Engine

- Hệ thống animation cấu hình trong `config.yml`.
- Dùng bằng cú pháp `%animation_<name>%`.
- Có sẵn mẫu:
  - `rainbow`
  - `wave`
  - `flash`
  - `scroll`
- Có thể tự thêm animation riêng bằng danh sách frame.
- Dùng được trong:
  - MOTD
  - Header/Footer
  - Scoreboard
  - BossBar
  - Broadcast
  - Title
  - ActionBar

### Placeholder

- Placeholder nội bộ:
  - `%server%`
  - `%online%`
  - `%max%`
  - `%player%`
  - `%ping%`
  - `%health%`
  - `%world%`
- Hỗ trợ PlaceholderAPI nếu server cài plugin PlaceholderAPI.
- Có hệ thống placeholder nội bộ để mở rộng trong code.

### RGB / Gradient

- Hỗ trợ màu legacy `&`.
- Hỗ trợ RGB dạng `&#RRGGBB`.
- Hỗ trợ Gradient dạng `<#RRGGBB>text</#RRGGBB>`.
- Có cơ chế downsample màu về legacy gần nhất cho client cũ.

### Database

- Hỗ trợ SQLite mặc định.
- Hỗ trợ MySQL.
- Lưu trạng thái bật/tắt BossBar/Scoreboard của người chơi.
- Sử dụng HikariCP đã được đóng gói vào plugin.

---

## API cho developer

SoCore có module `SoCore-api` và `SoCore-common` để mở rộng trong tương lai.

Mục tiêu API:

- Truy cập instance plugin.
- Định dạng màu RGB/Gradient.
- Đăng ký placeholder tùy chỉnh.
- Điều khiển Scoreboard.
- Điều khiển BossBar.
- Gửi Title/ActionBar/Broadcast qua code.
- Tùy chỉnh NameTag prefix/suffix.
- Tạo animation custom.

Ví dụ ý tưởng API:

```java
SoCoreAPI api = SoCoreAPI.getInstance();
String formatted = api.formatRgb("&#00FFFFHello World");
```

Lưu ý: API hiện đang ở giai đoạn BETA và sẽ được mở rộng dần.

---

## Cài đặt

1. Build hoặc tải file JAR.
2. Dùng bản Bukkit cho server Paper/Spigot:
   - `SoCore-bukkit-1.0.0-SNAPSHOT.jar`
3. Đặt file vào thư mục:
   - `plugins/`
4. Khởi động server.
5. Chỉnh file:
   - `plugins/SoCore/config.yml`
6. Reload bằng:
   - `/socore reload`

---

## Lệnh

| Lệnh | Mô tả | Quyền |
|---|---|---|
| `/socore help` | Xem hướng dẫn sử dụng | `admin.SoCore` |
| `/sc help` | Alias của `/socore help` | `admin.SoCore` |
| `/socore reload` | Reload toàn bộ config | `admin.SoCore` |
| `/socore reload <feature>` | Reload riêng từng tính năng | `admin.SoCore` |
| `/socore toggle scoreboard` | Bật/tắt scoreboard cá nhân | `admin.SoCore` |
| `/socore toggle bossbar` | Bật/tắt bossbar cá nhân | `admin.SoCore` |
| `/socore toggle <feature>` | Bật/tắt tính năng toàn cục | `admin.SoCore` |
| `/socore gui` | Mở GUI quản lý | `admin.SoCore` |
| `/socore broadcast <id>` | Gửi thông báo cưỡng bức | `admin.SoCore` |
| `/socore cpu` | Xem thông tin hiệu năng | `admin.SoCore` |

---

## Quyền

| Quyền | Mô tả |
|---|---|
| `admin.SoCore` | Quyền quản trị chính |
| `socore.admin` | Quyền quản trị phụ |
| `socore.group.admin` | Nhóm NameTag Admin |
| `socore.group.mod` | Nhóm NameTag Mod |

---

## Cấu trúc dự án

```text
SoCore/
├── SoCore-api/        # API public cho developer
├── SoCore-common/     # Code dùng chung: color, animation, placeholder, database
├── SoCore-bukkit/     # Plugin Bukkit / Spigot / Paper
├── SoCore-bungee/     # Module BungeeCord
└── SoCore-velocity/   # Module Velocity
```

---

## Build từ source

Yêu cầu:

- Java 8+
- Maven 3.x

Lệnh build:

```bash
mvn clean package
```

File Bukkit sau khi build:

```text
SoCore-bukkit/target/SoCore-bukkit-1.0.0-SNAPSHOT.jar
```

---

## Hỗ trợ

Plugin đang trong giai đoạn BETA. Nếu gặp lỗi, vui lòng liên hệ:

- Discord: https://discord.gg/ktdKcgJgqn
- Facebook: https://www.facebook.com/ngthlun/
- Zalo: 0792252408

---

## Donate

Nếu plugin hữu ích, hãy donate để ủng hộ chủ Plugin.

- Số Tài Khoản: `192483`
- Ngân Hàng: `MB Bank`
- Chủ Tài Khoản: `NGUYEN THANH LUAN`

---

## Ghi chú

SoCore là plugin đang phát triển. Một số tính năng nâng cao như Layout 80 slot, global playerlist proxy, NMS packet nâng cao sẽ tiếp tục được hoàn thiện trong các bản sau.
