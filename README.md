# Automated Deployment — bản phát hành

Repo này **chỉ chứa bản phát hành** của tool Automated Deployment (nâng cấp, đẩy cấu hình, chạy ATP cho thiết bị Juniper/Huawei). Mã nguồn nằm ở repo riêng, không công khai.

## Cài đặt

1. Vào [Releases](../../releases), tải `atp-client-{version}-win-x64.zip` của bản mới nhất.
2. (Nên làm) Kiểm sha256 so với file `.sha256` cùng tên:
   ```powershell
   Get-FileHash .\atp-client-X.Y.Z-win-x64.zip -Algorithm SHA256
   ```
3. Giải nén vào một thư mục (ví dụ `D:\AutomatedDeployment\`), chạy `AutomatedDeployment.exe`.

Tool lưu `config.json` và thư mục `data/` cạnh file exe. Khi cập nhật, tool tự tải bản mới từ repo này, kiểm sha256, chép đè các file chạy và **giữ nguyên** `config.json`, `data/`.

## Quy ước phát hành

| Mục | Quy ước |
|---|---|
| Tag | `vMAJOR.MINOR.PATCH` |
| Asset | `atp-client-{version}-win-x64.zip` và `atp-client-{version}-win-x64.zip.sha256` |
| Nội dung zip | File chạy ở cấp gốc (`AutomatedDeployment.exe`, `_internal/`); không có `config.json`, `data/` |

Bản build chưa ký số: Windows SmartScreen có thể hỏi lại lần đầu chạy ("More info" → "Run anyway").
