# [en] Split 2 RAID 1 Arrays on QNAP TR-004 and Use in Ubuntu

## 🎯 Goal:
Create 2 independent RAID 1 arrays on a QNAP TR-004:
- 2 HDDs → RAID 1
- 2 SSDs → RAID 1  
Then plug into Ubuntu and have both arrays recognized as separate drives.

## 🧰 Requirements:
- QNAP TR-004 (latest firmware)
- macOS machine for initial setup
- **QNAP External RAID Manager** app
- 2 matching HDDs + 2 matching SSDs
- All data will be erased during setup

## ⚠️ Important Notes:
1. **Set the rear RAID switch on TR-004 to “S/W” (Software Control Mode)**  
   → Required to allow RAID configuration via software.
2. **All existing data will be wiped when creating new RAID arrays**

## ⚙️ Steps:

### Step 1: Insert drives into TR-004
- Slots 1–2: HDDs
- Slots 3–4: SSDs

### Step 2: Set hardware RAID switch on the back to **S/W**

### Step 3: Connect TR-004 to macOS via USB

### Step 4: Open **QNAP External RAID Manager**
- Download from [QNAP official site](https://www.qnap.com/en/utilities/essentials)

### Step 5: Create 2 RAID 1 groups:
- Select the 2 HDDs → Create RAID 1
- Select the 2 SSDs → Create RAID 1
- Apply config and wait for sync

### Step 6: Disconnect from Mac → Plug into Ubuntu

## 🐧 **On Ubuntu:**
Run `lsblk`:
```
sda    1.8T  ← RAID 1 from HDDs
sdb    465G  ← RAID 1 from SSDs
```
You can format, partition, mount as you like. No `mdadm` required — arrays show as regular physical disks.

## ✅ Conclusion:
- TR-004 supports **2 separate RAID 1 arrays** when in Software Control Mode
- QNAP software on macOS allows selecting drives for separate groups
- Ubuntu detects them cleanly as separate drives
- No special drivers or setup needed — stable and cross-platform

---

# [vi] QNAP TR-004: Tạo 2 RAID 1 Riêng Biệt và Dùng Trên Ubuntu

## 🎯 Mục tiêu
Tạo 2 RAID 1 riêng biệt trên QNAP TR-004:
- 2 ổ HDD → RAID 1
- 2 ổ SSD → RAID 1  
Sau đó gắn vào Ubuntu và hệ thống nhận như 2 ổ đĩa độc lập.

---

## 🧰 Yêu cầu
- QNAP TR-004 (firmware mới)
- Máy macOS để cấu hình ban đầu
- Phần mềm **QNAP External RAID Manager**
- 2 HDD + 2 SSD (kích thước tương đương)
- **Lưu ý: toàn bộ dữ liệu cũ sẽ bị xoá**

---

## ⚠️ Lưu ý quan trọng
- **Gạt công tắc RAID phía sau TR-004 về chế độ “S/W” (Software Control)**  
  Nếu không, phần mềm sẽ không cấu hình được RAID theo nhóm.
- **Tạo RAID mới sẽ xoá sạch dữ liệu tất cả ổ đĩa**  
  Nhớ **backup trước khi thực hiện**.

---

## ⚙️ Các bước thực hiện

### 1. Gắn ổ vào TR-004
- Slot 1–2: HDD
- Slot 3–4: SSD

### 2. Gạt công tắc RAID phía sau về chế độ **S/W**

### 3. Gắn TR-004 vào máy Mac qua USB

### 4. Mở ứng dụng **QNAP External RAID Manager**
- Tải tại: [https://www.qnap.com/en/utilities/essentials](https://www.qnap.com/en/utilities/essentials)

### 5. Tạo 2 RAID 1 Group
- Chọn 2 HDD → tạo RAID 1
- Chọn 2 SSD → tạo RAID 1
- Apply cấu hình, chờ sync xong

### 6. Rút TR-004 khỏi Mac, cắm vào máy Ubuntu

---

## 🐧 Trên Ubuntu
Chạy `lsblk`, bạn sẽ thấy:
```
sda    1.8T  ← RAID 1 from HDDs
sdb    465G  ← RAID 1 from SSDs

```

Bạn có thể chia phân vùng, mount, định dạng tùy ý. Không cần `mdadm`, Ubuntu coi mỗi RAID như một ổ cứng vật lý.

## ✅ Tổng kết:
- TR-004 hỗ trợ chia RAID thành 2 nhóm nếu dùng Software Control Mode
- QNAP External RAID Manager trên macOS **cho phép chọn từng ổ để tạo RAID**
- Sau khi tạo, Ubuntu nhận RAID như 2 ổ riêng biệt
- Hoạt động ổn định, không cần phần mềm RAID trên Linux
