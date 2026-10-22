# CoAP Lab Python

## Thong tin thuc hien

- Ho va ten: Nguyen Van A
- Ma sinh vien: B23DCCN001
- Mon hoc: IoT va ung dung

Thay doi hai gia tri trong `coap_client_bai1.py` truoc khi nop bai.

## Moi truong

- Python 3.9 tro len
- Thu vien: aiocoap
- Dia chi Server: `127.0.0.1`
- Cong CoAP UDP: `5683`

Cai dat thu vien:

```powershell
py -m pip install -r requirements.txt
```

Neu may tinh chua co Python, cai Python 3 tu trang chinh thuc va chon tuy chon them Python vao PATH.

## Bai 1 Gui va nhan thong diep CoAP

Terminal 1:

```powershell
py coap_server_bai1.py
```

Terminal 2:

```powershell
py coap_client_bai1.py
```

URI: `coap://127.0.0.1:5683/iot/lab/message`

Server xu ly GET va POST, in noi dung POST cung thoi diem nhan. GET tra ve loi chao va kem thong diep POST gan nhat neu co.

## Bai 2 Giam sat cam bien nhiet do va do am

Terminal 1:

```powershell
py sensor_server_bai2.py
```

Terminal 2:

```powershell
py monitor_client_bai2.py
```

URI: `coap://127.0.0.1:5683/iot/lab/sensor01/data`

Sensor Server cap nhat du lieu moi sau moi 3 giay va tra JSON. Monitoring Client truy van moi 3 giay, hien thi du lieu va canh bao khi nhiet do tren 35 C hoac do am duoi 40 %.

## Bai 3 Giam sat va dieu khien den voi CoAP Observe

Terminal 1:

```powershell
py light_server_bai3.py
```

Terminal 2:

```powershell
py light_monitor_bai3.py
```

Terminal 3:

```powershell
py light_controller_bai3.py
```

URI: `coap://127.0.0.1:5683/iot/lab/light01/status`

Controller chap nhan `ON`, `OFF`, `STATUS`, `EXIT`. Monitoring Client dang ky CoAP Observe, khong su dung GET dinh ky. Nhan Ctrl+C de dung Server, Monitoring Client hoac Sensor Monitoring Client.

## Ket qua dat duoc

- Bai 1: Client GET va POST thanh cong, Server phan hoi va luu thong diep gan nhat.
- Bai 2: Server tra du lieu JSON cho cam bien `sensor01`; Client hien thi va canh bao theo nguong.
- Bai 3: Controller thay doi trang thai bang PUT; Monitoring Client nhan thong bao qua CoAP Observe khi trang thai thay doi.

Khi chay tren hai may khac nhau, thay `127.0.0.1` trong cac file Client bang IP cua may chay Server va cho phep UDP cong 5683 tren tuong lua.
