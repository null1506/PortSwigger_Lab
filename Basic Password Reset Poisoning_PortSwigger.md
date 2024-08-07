---
title: Basic Password Reset Poisoning_PortSwigger

---

Chọn Go to exploit server ( đây là server của ta, ta sẽ dùng nó để lừa server của web thật, rằng đây là host thật, sau đó server đó sẽ xài domain server của ta, gửi email có chứa link domain server của ta kèm token về cho người dùng )
![image](https://hackmd.io/_uploads/H1cRHg-c0.png)

![image](https://hackmd.io/_uploads/HyByUeZcR.png)

Ta thay host thành đường dẫn của exploit server

![image](https://hackmd.io/_uploads/HJXTIeb50.png)
![image](https://hackmd.io/_uploads/HkAp8eZ5R.png)
Chọn Forward
Tắt intercept đi
ta thấy hiện thông báo email đã được gửi về cho người dùng, trong email này sẽ chứa đường link độc (link chứa domain server của ta kèm token server thật gửi về), sau đó người dùng sẽ nhấn vô link đó, exploit server sẽ trả về cho ta đường link mà người dùng click vô
![image](https://hackmd.io/_uploads/BkuywxW9A.png)
Qua exploit server để check 
Chọn Access Log
![image](https://hackmd.io/_uploads/S1aDPe-90.png)

Ta thấy đường dẫn là 
/exploit/forgot-password?temp-forgot-password-token=z5kc0l0ohc2kipmmybye3wsjhocz78jv
![image](https://hackmd.io/_uploads/BkjOvlb9A.png)
Ta thay /exploit thành https://0a8f002203b75cf9802808d3000100fd.web-security-academy.net
![image](https://hackmd.io/_uploads/H1IjDx-cR.png)
--> https://0a8f002203b75cf9802808d3000100fd.web-security-academy.net/forgot-password?temp-forgot-password-token=z5kc0l0ohc2kipmmybye3wsjhocz78jv
Ta truy cập vào đường dẫn trên ( đó chính là link reset password ), đặt lại pass là abc
![image](https://hackmd.io/_uploads/rkQ0Dg-qA.png)
Đăng nhập lại vào tk carlos
![image](https://hackmd.io/_uploads/H1VMdeWq0.png)
Hoàn thành
![image](https://hackmd.io/_uploads/H1Fm_xbqR.png)
