# AEHolograms - Wiki Hướng Dẫn Sử Dụng
---

## Mục Lục

1. [Giới Thiệu](#-giới-thiệu)
2. [Cài Đặt](#-cài-đặt)
3. [Lệnh Cơ Bản](#-lệnh-cơ-bản)
4. [Tạo Hologram](#-tạo-hologram)
5. [Quản Lý Dòng (Lines)](#-quản-lý-dòng-lines)
6. [Quản Lý Trang (Pages)](#-quản-lý-trang-pages)
7. [Animation Hệ Thống](#-animation-hệ-thống)
8. [Loại Hologram](#-loại-hologram)
9. [Actions & Click Events](#-actions--click-events)
10. [Cấu Hình](#-cấu-hình)
11. [Permissions](#-permissions)
12. [Mẹo & Thủ Thuật](#-mẹo--thủ-thuật)
13. [FAQ](#-faq)

---

## Giới Thiệu

**AEHolograms** là một plugin hologram mạnh mẽ cho Minecraft, hỗ trợ từ phiên bản **1.8.x đến 1.21.x**. Plugin cung cấp các tính năng:

- ✅ Hologram text với animation đa dạng
- ✅ Hologram items, heads, entities
- ✅ Hệ thống trang (pages) và click actions
- ✅ Tương thích PlaceholderAPI & HeadDatabase  
- ✅ Damage & Healing display
- ✅ Performance cao, tối ưu hóa tốt

---

## Lệnh Cơ Bản

### Lệnh Chính
```
/aeholograms [args]
Aliases: /aeholo, /holograms, /holo, /aeh
```

### Danh Sách Lệnh Quan Trọng

| Lệnh | Mô Tả | Ví Dụ |
|------|-------|-------|
| `/aeh help` | Hiển thị trợ giúp | |
| `/aeh version` | Xem phiên bản plugin | |
| `/aeh reload` | Tải lại plugin | |
| `/aeh list [page]` | Danh sách hologram | `/aeh list 1` |

---

## Tạo Hologram

### Tạo Hologram Cơ Bản

```code
# Tạo hologram text đơn giản
Command: /aeh create MyFirstHolo Hello World!
Result: Tạo hologram tên "MyFirstHolo" với nội dung "Hello World!"

# Tạo hologram tại vị trí cụ thể  
Command: /aeh create MyHolo -l:world:100:64:200 Welcome to server!
Result: Tạo hologram tại tọa độ cụ thể trong world

# Tạo hologram căn giữa block
Command: /aeh create MyHolo --center Hello everyone!
Result: Tạo hologram căn giữa block hiện tại
```

### Lệnh Quản Lý Hologram

| Lệnh | Mô Tả | Ví Dụ |
|------|-------|-------|
| `/aeh h create <name> [content]` | Tạo hologram mới | `/aeh h create welcome Hello!` |
| `/aeh h delete <hologram>` | Xóa hologram | `/aeh h delete welcome` |
| `/aeh h clone <hologram> <name>` | Sao chép hologram | `/aeh h clone welcome welcome2` |
| `/aeh h info <hologram>` | Xem thông tin | `/aeh h info welcome` |
| `/aeh h teleport <hologram>` | Dịch chuyển đến hologram | `/aeh h tp welcome` |
| `/aeh h movehere <hologram>` | Di chuyển hologram đến bạn | `/aeh h movehere welcome` |
| `/aeh h enable/disable <hologram>` | Bật/tắt hologram | `/aeh h enable welcome` |

### Tùy Chỉnh Hologram

```code
# Căn chỉnh hologram
Command: /aeh h align <holo1> <X|Y|Z|XZ|FACE> <holo2>
Example: /aeh h align welcome X spawn
Description: Căn chỉnh hologram welcome với hologram spawn theo trục X

# Di chuyển hologram
Command: /aeh h move <hologram> <x> <y> <z>
Example: /aeh h move welcome ~5 ~ ~-2
Description: Di chuyển hologram tương đối (+5 X, không đổi Y, -2 Z)

# Đặt hướng quay
Command: /aeh h setfacing <hologram> <NORTH|SOUTH|EAST|WEST|degrees>
Example: /aeh h setfacing welcome NORTH
Description: Quay hologram về hướng Bắc

# Cài đặt quyền xem
Command: /aeh h setpermission <hologram> [permission]
Example: /aeh h perm welcome hologram.vip
Description: Chỉ player có quyền "hologram.vip" mới thấy hologram
```

---

## Quản Lý Dòng (Lines)

### Lệnh Cơ Bản

```code
# Xem danh sách dòng
Command: /aeh l lines <hologram> <page> [listPage]
Example: /aeh l lines welcome 1
Description: Hiển thị tất cả dòng trong trang 1 của hologram welcome

# Thêm dòng
Command: /aeh l add <hologram> <page> [content]
Example: /aeh l add welcome 1 New line here!
Description: Thêm dòng mới vào cuối trang

# Chèn dòng
Command: /aeh l insert <hologram> <page> <line> [content]
Example: /aeh l insert welcome 1 2 Insert at position 2
Description: Chèn dòng tại vị trí số 2

# Sửa dòng
Command: /aeh l set <hologram> <page> <line> <content>
Example: /aeh l set welcome 1 1 Updated first line
Description: Thay đổi nội dung dòng số 1

# Xóa dòng
Command: /aeh l remove <hologram> <page> <line>
Example: /aeh l rem welcome 1 2
Description: Xóa dòng số 2
```

### Tùy Chỉnh Dòng

```code
# Điều chỉnh chiều cao dòng
Command: /aeh l height <hologram> <page> <line> <height>
Example: /aeh l height welcome 1 1 0.5
Description: Đặt chiều cao dòng 1 = 0.5 blocks (0.0-2.5)

# Điều chỉnh offset X/Z
Command: /aeh l offsetx <hologram> <page> <line> <offset>
Example: /aeh l offsetx welcome 1 1 -0.3
Description: Dịch dòng sang trái 0.3 blocks (-2.5 đến 2.5)

Command: /aeh l offsetz <hologram> <page> <line> <offset>
Example: /aeh l offsetz welcome 1 1 0.2
Description: Dịch dòng về phía trước 0.2 blocks

# Căn chỉnh dòng
Command: /aeh l align <hologram> <page> <line1> <line2> <X|Z|XZ|FACE>
Example: /aeh l align welcome 1 1 2 XZ
Description: Căn chỉnh dòng 1 với dòng 2 theo trục X và Z

# Hoán đổi dòng
Command: /aeh l swap <hologram> <page> <line1> <line2>
Example: /aeh l swap welcome 1 1 3
Description: Đổi chỗ dòng 1 với dòng 3

# Đặt quyền cho dòng
Command: /aeh l setpermission <hologram> <page> <line> [permission]
Example: /aeh l perm welcome 1 1 vip.access
Description: Chỉ player có quyền "vip.access" mới thấy dòng này

# Đặt hướng quay cho dòng
Command: /aeh l setfacing <hologram> <page> <line> <facing>
Example: /aeh l setfacing welcome 1 1 SOUTH
Description: Quay dòng về hướng Nam
```

---

## Quản Lý Trang (Pages)

### Lệnh Cơ Bản

```code
# Thêm trang
Command: /aeh p add <hologram> [content]
Example: /aeh p add welcome Page 2 content
Description: Thêm trang mới vào cuối hologram với nội dung

# Chèn trang
Command: /aeh p insert <hologram> <page> [content]
Example: /aeh p insert welcome 2 Middle page
Description: Chèn trang mới tại vị trí số 2

# Xóa trang
Command: /aeh p remove <hologram> <page>
Example: /aeh p rem welcome 2
Description: Xóa trang số 2 khỏi hologram

# Hoán đổi trang
Command: /aeh p swap <hologram> <page1> <page2>
Example: /aeh p swap welcome 1 2
Description: Đổi chỗ trang 1 với trang 2

# Chuyển đổi trang
Command: /aeh p switch <hologram> <page> [player]
Example: /aeh p switch welcome 2
Description: Chuyển hologram sang hiển thị trang 2
```

### Actions Cho Trang

```code
# Thêm action khi click
Command: /aeh p addaction <hologram> <page> <clickType> <action>
Example: /aeh p addaction welcome 1 LEFT [CONSOLE] say Hello!
Description: Thêm action chạy lệnh console khi click trái

# Xem danh sách actions
Command: /aeh p actions <hologram> <page> <clickType>
Example: /aeh p actions welcome 1 LEFT
Description: Hiển thị tất cả action click trái của trang 1

# Xóa action
Command: /aeh p removeaction <hologram> <page> <clickType> <index>
Example: /aeh p removeaction welcome 1 LEFT 1
Description: Xóa action số 1 trong danh sách click trái

# Xóa tất cả actions
Command: /aeh p clearactions <hologram> <page> <clickType>
Example: /aeh p clearactions welcome 1 LEFT
Description: Xóa tất cả action click trái của trang 1
```

**Click Types:**
- `LEFT` - Click trái
- `RIGHT` - Click phải  
- `SHIFT_LEFT` - Shift + Click trái
- `SHIFT_RIGHT` - Shift + Click phải

**Action Types:**
- `[PLAYER] <command>` - Chạy lệnh bằng player
- `[CONSOLE] <command>` - Chạy lệnh bằng console
- `[MESSAGE] <text>` - Gửi tin nhắn
- `[ACTIONBAR] <text>` - Hiển thị action bar
- `[CONNECT] <server>` - Kết nối BungeeCord
- `[SOUND] <sound>:<volume>:<pitch>` - Phát âm thanh

---

## Animation Hệ Thống

### Animation Có Sẵn

#### 1. **Typewriter Animation**
Hiệu ứng đánh máy từng ký tự
```
<#ANIM:typewriter>Hello World!</#ANIM>
{#ANIM:typewriter:speed,delay}Text here{/#ANIM}
```

#### 2. **Wave Animation** 
Hiệu ứng sóng với màu sắc
```
<#ANIM:wave:&a:&e>Rainbow Wave!</#ANIM>
{#ANIM:wave:&c:&6}Red to Gold Wave{/#ANIM}
```

#### 3. **Scroll Animation**
Hiệu ứng cuộn ngang
```
<#ANIM:scroll>This text scrolls horizontally</#ANIM>
{#ANIM:scroll:speed}Faster scroll{/#ANIM}
```

#### 4. **Burn Animation**
Hiệu ứng cháy
```
<#ANIM:burn>Burning text effect!</#ANIM>
```

#### 5. **Colors Animation**
Hiệu ứng đổi màu cầu vồng
```
<#ANIM:colors>Rainbow Colors!</#ANIM>
&u (shortcut for colors animation)
```

### Custom Animations

Tạo animation tùy chỉnh trong thư mục `plugins/AEHolograms/animations/`:

```code
# myanimation.yml
name: "myanimation"
speed: 5
delay: 10
frames:
  - "&cFrame 1"
  - "&6Frame 2"
  - "&eFrame 3"
  - "&aFrame 4"
```

Sử dụng:
```
<#ANIM:myanimation>Text with custom animation</#ANIM>
```

---

## Loại Hologram

### 1. **Text Hologram**
```code
# Text đơn giản với màu sắc
Command: /aeh l add welcome 1 &6Hello &bWorld!
Description: Tạo dòng text màu vàng và xanh dương

# Text với animation
Command: /aeh l add welcome 1 <#ANIM:wave:&c:&6>Animated Text</#ANIM>
Description: Text với hiệu ứng sóng đổi màu từ đỏ sang vàng
```

### 2. **Icon Hologram** 
```code
# Icon cơ bản
Command: /aeh l add welcome 1 #ICON: DIAMOND
Description: Hiển thị item kim cương floating

# Icon với hiệu ứng enchanted
Command: /aeh l add welcome 1 #ICON: DIAMOND_SWORD !ENCHANTED
Description: Kiếm kim cương với hiệu ứng enchanted (ánh sáng)

# Icon với player head
Command: /aeh l add welcome 1 #ICON: PLAYER_HEAD (PlayerName)
Description: Hiển thị đầu của player cụ thể

# Các loại icon phổ biến
Examples:
  - "#ICON: EMERALD" → Ngọc lục bảo
  - "#ICON: GOLD_INGOT" → Thỏi vàng  
  - "#ICON: NETHER_STAR !ENCHANTED" → Nether star phát sáng
  - "#ICON: TOTEM_OF_UNDYING" → Totem bất tử
  - "#ICON: ELYTRA" → Cánh elytra
```

### 3. **Head Hologram** 
```code
# Player head cơ bản
Command: /aeh l add welcome 1 #HEAD: PLAYER_HEAD (Notch)
Description: Hiển thị head của Notch (kích thước lớn)

# Head với placeholder
Command: /aeh l add welcome 1 #HEAD: PLAYER_HEAD (%player_name%)
Description: Head của player hiện tại (cần PlaceholderAPI)

# Small head (nhỏ hơn)
Command: /aeh l add welcome 1 #SMALLHEAD: PLAYER_HEAD (Steve)
Description: Head nhỏ của Steve

# HeadDatabase integration (nếu có plugin)
Command: /aeh l add welcome 1 #HEAD: PLAYER_HEAD (HEADDATABASE_1234)
Description: Sử dụng head từ HeadDatabase với ID 1234

# Custom texture head
Command: /aeh l add welcome 1 #HEAD: PLAYER_HEAD (TEXTURE:eyJ0ZXh0dXJlcy...)
Description: Sử dụng texture tùy chỉnh (base64)

# Các ví dụ head phổ biến
Popular Examples:
  - "(Notch)" → Head của Notch
  - "(Herobrine)" → Head của Herobrine  
  - "(MHF_Steve)" → Head Steve mặc định
  - "(MHF_Alex)" → Head Alex mặc định
  - "(MHF_Creeper)" → Head Creeper
  - "(MHF_Zombie)" → Head Zombie
  - "(MHF_Skeleton)" → Head Skeleton
  - "(MHF_Spider)" → Head Spider
  - "(MHF_Enderman)" → Head Enderman
  - "(MHF_Villager)" → Head Villager
```

### 4. **Entity Hologram**
```code
# Entity cơ bản
Command: /aeh l add welcome 1 #ENTITY: VILLAGER
Description: Hiển thị villager 3D

# Các entity phổ biến
Popular Examples:
  - "#ENTITY: ZOMBIE" → Zombie
  - "#ENTITY: SKELETON" → Skeleton
  - "#ENTITY: CREEPER" → Creeper
  - "#ENTITY: COW" → Bò
  - "#ENTITY: PIG" → Heo
  - "#ENTITY: CHICKEN" → Gà
  - "#ENTITY: HORSE" → Ngựa
  - "#ENTITY: WOLF" → Chó sói
  - "#ENTITY: CAT" → Mèo
  - "#ENTITY: DRAGON" → Rồng (Ender Dragon)
  - "#ENTITY: WITHER" → Wither Boss
```

### **Hướng Dẫn Chi Tiết Tạo Icon & Head**

#### **A. Tạo Icon Shop Hologram**
```code
Step 1: Tạo hologram cơ bản
Command: /aeh create itemshop Item Shop

Step 2: Thêm tiêu đề
Command: /aeh l add itemshop 1 &6&l⚡ ITEM SHOP ⚡

Step 3: Thêm icon kim cương
Command: /aeh l add itemshop 1 #ICON: DIAMOND !ENCHANTED

Step 4: Thêm mô tả
Command: /aeh l add itemshop 1 &eClick to buy items!

Step 5: Thêm action mở shop
Command: /aeh p addaction itemshop 1 LEFT [PLAYER] shop
```

#### **B. Tạo Player Info Hologram**
```code
Step 1: Tạo hologram player info
Command: /aeh create playerinfo Player Info

Step 2: Thêm head của player
Command: /aeh l add playerinfo 1 #HEAD: PLAYER_HEAD (%player_name%)

Step 3: Thêm tên player
Command: /aeh l add playerinfo 1 &6Player: &e%player_name%

Step 4: Thêm thông tin
Command: /aeh l add playerinfo 1 &7Health: &c%player_health%/20
Command: /aeh l add playerinfo 1 &7Level: &a%player_level%
```

#### **C. Tạo Boss Hologram**
```code
Step 1: Tạo hologram boss
Command: /aeh create boss Boss Arena

Step 2: Thêm entity boss
Command: /aeh l add boss 1 #ENTITY: WITHER

Step 3: Thêm tên boss với animation
Command: /aeh l add boss 1 <#ANIM:colors>&l⚡ WITHER BOSS ⚡</#ANIM>

Step 4: Thêm thông tin
Command: /aeh l add boss 1 &cHealth: &f10000/10000 ❤
Command: /aeh l add boss 1 &7Click to challenge!

Step 5: Thêm action
Command: /aeh p addaction boss 1 LEFT [PLAYER] boss fight wither
```

#### **D. Tips Cho Icon & Head**
```code
Icon Tips:
  - Sử dụng "!ENCHANTED" để tạo hiệu ứng phát sáng
  - Kết hợp với animation để tạo hiệu ứng động
  - Đặt chiều cao phù hợp với /aeh l height

Head Tips:  
  - #HEAD cho head kích thước bình thường
  - #SMALLHEAD cho head nhỏ gọn
  - Sử dụng MHF_ prefix cho mob heads
  - Kết hợp với PlaceholderAPI cho head động

Best Practices:
  - Icon thường dùng cho shop, menu, decoration
  - Head thường dùng cho player info, leaderboard
  - Entity thường dùng cho boss, pet, decoration
  - Kết hợp nhiều loại để tạo hologram đa dạng
```

---

## Actions & Click Events

### Cú Pháp Actions

```code
# Lệnh player
Command: /aeh p addaction welcome 1 LEFT [PLAYER] spawn
Description: Player chạy lệnh "/spawn"

# Lệnh console  
Command: /aeh p addaction welcome 1 RIGHT [CONSOLE] give %player% diamond 1
Description: Console chạy lệnh give diamond cho player

# Tin nhắn
Command: /aeh p addaction welcome 1 LEFT [MESSAGE] &aWelcome to server!
Description: Gửi tin nhắn màu xanh lá đến player

# Action bar
Command: /aeh p addaction welcome 1 RIGHT [ACTIONBAR] &eYou clicked the hologram!
Description: Hiển thị text trên action bar (trên hotbar)

# Âm thanh
Command: /aeh p addaction welcome 1 LEFT [SOUND] ENTITY_EXPERIENCE_ORB_PICKUP:1.0:1.5
Description: Phát âm thanh (sound:volume:pitch)

# Kết nối server (BungeeCord)
Command: /aeh p addaction welcome 1 RIGHT [CONNECT] lobby
Description: Chuyển player sang server "lobby"
```

### Ví Dụ Actions Phức Tạp

```code
# Cửa hàng hologram
Step 1: /aeh create shop Shop
Step 2: /aeh l add shop 1 &6&l[SHOP]
Step 3: /aeh l add shop 1 &eClick để mở shop!
Step 4: /aeh p addaction shop 1 LEFT [PLAYER] shop
Step 5: /aeh p addaction shop 1 LEFT [SOUND] UI_BUTTON_CLICK:1.0:1.0
Result: Tạo hologram shop với âm thanh khi click

# Teleport hologram  
Step 1: /aeh create spawn Spawn
Step 2: /aeh l add spawn 1 &a&lSPAWN
Step 3: /aeh l add spawn 1 &7Click để về spawn
Step 4: /aeh p addaction spawn 1 LEFT [PLAYER] spawn
Step 5: /aeh p addaction spawn 1 LEFT [MESSAGE] &aTeleported to spawn!
Result: Hologram teleport với thông báo xác nhận
```

---

## Cấu Hình

### File config.yml

```code
defaults:
  text: "Blank Line"
  display-range: 48      # Phạm vi hiển thị (blocks)
  update-range: 48       # Phạm vi cập nhật (blocks) 
  update-interval: 20    # Thời gian cập nhật (ticks)
  lru-cache-size: 500    # Kích thước cache
  
  # Chiều cao mặc định cho từng loại
  height:
    text: 0.3
    icon: 0.6
    head: 0.75
    smallhead: 0.6
    
  down-origin: false     # Gốc tọa độ từ dưới lên

# Thời gian cooldown click (ticks)
click-cooldown: 1

# Cho phép placeholder trong animation (tốn CPU)
allow-placeholders-inside-animations: false

# Cập nhật hologram khi teleport
update-visibility-on-teleport: false

# Hologram ở tầm mắt player
holograms-eye-level-positioning: false

# Timeout kết nối skin (giây)
player-skin-connection-timeout: 5

# Hiển thị damage
damage-display:
  enabled: false
  players: false
  mobs: false
  zero-damage: false
  duration: 40           # Thời gian hiển thị (ticks)
  appearance: '&c{damage}'
  critical-appearance: '&4&lCrit!&4 {damage}'
  height: 0

# Hiển thị healing
healing-display:
  enabled: false
  players: false
  mobs: false
  duration: 40
  appearance: '&a+ {heal}'
  height: 0

# Ký tự thay thế tùy chỉnh
custom-replacements:
  '[x]': '█'
  '[X]': '█'
  '[/]': '▌'
  '[,]': '░'
  '[,,]': '▒'
  '[,,,]': '▓'
  '[p]': '•'
  '[P]': '•'
  '[|]': '⎹'
```
---

## Permissions

### Permissions Chính

| Permission | Mô Tả | Mặc Định |
|------------|--------|----------|
| `aeholograms.admin` | Toàn bộ quyền admin | OP |
| `aeholograms.default` | Quyền cơ bản | True |
| `aeholograms.command` | Sử dụng lệnh | OP |

### Permissions Chi Tiết

```code
# Hologram Management
aeholograms.command.holograms.create
aeholograms.command.holograms.delete
aeholograms.command.holograms.edit
aeholograms.command.holograms.clone
aeholograms.command.holograms.teleport
aeholograms.command.holograms.movehere

# Line Management  
aeholograms.command.lines.add
aeholograms.command.lines.remove
aeholograms.command.lines.edit
aeholograms.command.lines.set

# Page Management
aeholograms.command.pages.add
aeholograms.command.pages.remove
aeholograms.command.pages.switch

# Utility
aeholograms.command.list
aeholograms.command.reload
aeholograms.command.help
```

---

## Mẹo & Thủ Thuật

### 1. **Sử Dụng PlaceholderAPI**

```code
# Player info hologram
Commands:
  - /aeh l add playerinfo 1 &6Player: &e%player_name%
  - /aeh l add playerinfo 1 &6Health: &c%player_health%/20
  - /aeh l add playerinfo 1 &6Location: &b%player_x%, %player_y%, %player_z%
Description: Tạo hologram hiển thị thông tin player động
```

### 2. **Hologram Động Với Animation**

```code
# Server info với animation
Steps:
  - Command: /aeh create serverinfo Server Status
    Description: Tạo hologram server status
  - Command: /aeh l add serverinfo 1 <#ANIM:colors>Welcome to our server!</#ANIM>
    Description: Text chào mừng với animation màu sắc
  - Command: /aeh l add serverinfo 1 &7Online: &a%server_online% &7/ &a%server_max%
    Description: Hiển thị số player online/tối đa
  - Command: /aeh l add serverinfo 1 <#ANIM:wave:&c:&6>Join us now!</#ANIM>
    Description: Text kêu gọi với animation sóng
```

### 3. **Menu Hologram**

```code
# Tạo menu chính
Setup:
  - Command: /aeh create mainmenu &6&l=== MENU ===
    Description: Tạo hologram menu với tiêu đề
  - Command: /aeh l add mainmenu 1 &a[SHOP] &7- Click to open shop
    Description: Option shop
  - Command: /aeh l add mainmenu 1 &b[WARP] &7- Teleport menu
    Description: Option warp
  - Command: /aeh l add mainmenu 1 &e[INFO] &7- Server information
    Description: Option info

# Thêm actions
Actions:
  - Command: /aeh p addaction mainmenu 1 LEFT [PLAYER] shop
    Description: Click trái mở shop
  - Command: /aeh p addaction mainmenu 1 RIGHT [PLAYER] warp
    Description: Click phải mở warp
```

### 4. **Hologram Trang Trí**

```code
# Biển chào mừng
Welcome Sign:
  - Command: /aeh create welcome Welcome
    Description: Tạo hologram chào mừng
  - Command: /aeh l add welcome 1 &6&l✦ &e&lWELCOME &6&l✦
    Description: Tiêu đề chào mừng với ký tự đặc biệt
  - Command: /aeh l add welcome 1 <#ANIM:typewriter>&7to our amazing server</#ANIM>
    Description: Mô tả với hiệu ứng đánh máy
  - Command: /aeh l add welcome 1 &8&o━━━━━━━━━━━━━━━━━━━
    Description: Đường phân cách
  - Command: /aeh l add welcome 1 #ICON: NETHER_STAR !ENCHANTED
    Description: Icon nether star phát sáng
  - Command: /aeh l add welcome 1 &8&o━━━━━━━━━━━━━━━━━━━
    Description: Đường phân cách dưới
```

### 5. **Performance Tips**

```code
Optimization Settings:
  - display-range: Đặt từ 32-48 blocks (mặc định 48)
  - update-range: Đặt từ 32-48 blocks (mặc định 48)
  - update-interval: Tăng lên 40-60 ticks nếu không cần update liên tục
  - allow-placeholders-inside-animations: false (nếu không dùng placeholder trong animation)

Best Practices:
  - Hạn chế số lượng animation cùng lúc (tối đa 5-10)
  - Tránh tạo quá nhiều hologram trong cùng một khu vực
  - Sử dụng quyền để giới hạn ai có thể thấy hologram
  - Định kỳ kiểm tra hologram không sử dụng và xóa bỏ
```

### 6. **Troubleshooting**

```code
# Kiểm tra hologram gần bạn
Command: /aeh h near 50
Description: Xem tất cả hologram trong bán kính 50 blocks

# Cập nhật hologram bị lỗi
Command: /aeh h update hologram_name
Description: Force update hologram khi bị lỗi hiển thị

# Reload plugin khi có vấn đề
Command: /aeh reload
Description: Tải lại toàn bộ plugin và config

# Kiểm tra thông tin chi tiết
Command: /aeh h info hologram_name
Description: Xem thông tin chi tiết của hologram

# Bật/tắt hologram
Commands:
  - /aeh h disable hologram_name (tắt hologram)
  - /aeh h enable hologram_name (bật hologram)
```

---

### Nếu có gì thắc mặc vui lòng liên hệ author tại [Facebook](https://www.facebook.com/tybzione/)
