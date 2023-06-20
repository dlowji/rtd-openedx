.. _configuration-alpha

=========================
Cài đặt và chạy Open edX
=========================

.. contents::
   :local:

.. toctree::
   Phiên bản phần mềm
   Phương thức cài đặt
   Cài đặt Open edX bằng Tutor :ref:`introduce-alpha`

Trước khi cài đặt Open edX, chúng ta cần phải xác định:
  * **Phiên bản phần mềm**
  * **Phương thức cài đặt**

Phiên bản phần mềm
==================
Hiện tại Open edX cung cấp 2 lựa chọn về phiên bản:
 * **Master**, có thể hiểu là phiên bản mã nguồn mới nhất, thậm chí còn mới hơn cả phiên bản mã nguồn mà tên miền `edx.org <https://www.edx.org/>`_ đang chạy ổn định.
 * **Release** là phiên bản mã nguồn được đánh dấu và thử nghiệm cho mục đích sử dụng rộng rãi. Các phiên bản này được đặt tên theo thứ tự bảng chữ cái tên các loài cây: Juniper, Koa, Lilac, ...

.. note:: 
Ở đây chúng ta chỉ nên cân nhắc chọn phiên bản **Master** trong trường hợp cần điều chỉnh và phát triển tiếp mã nguồn hoặc chúng ta cần một tính năng hoặc bản sửa lỗi mới nhưng chưa được chính thức áp dụng cho phía người dùng.

Phương thức cài đặt
===================
Các phương thức cài đặt hiện đang được Open edX hỗ trợ là:
 * **Tutor**: Một môi trường dựa trên `Docker <https://www.docker.com/>`_ được cộng đồng hỗ trợ phù hợp cho môi trường production và development.
 * **Native**: Cung cấp phương thức cài đặt sẵn sàng để đẩy lên môi trường production bằng cách sử dụng Ansible Playbook.
 * **Devstack**: Môi trường phát triển dựa trên `Docker <https://www.docker.com/>`_, sẽ hữu ích nếu chúng ta muốn sữa đổi mã nguồn Open edX trên các thiết bị cục bộ, chẳng hạn như máy tính cá nhân hoặc máy chủ trong mạng nội bộ.
Việc chọn phương thức cài đặt tùy thuộc vào mục đích của chúng ta:

   =============================================== ========= ==================
   Mục đích/Kịch bản                               Phiên bản Lựa chọn
   =============================================== ========= ==================
   Chạy môi trường production                      Release   Tutor hoặc Native
   Cài đặt môi trường kiểm thử tương tự production Release   Tutor hoặc Native
   Cài đặt môi trường kiểm thử tương tự production Master    Native
   Sửa đổi mã nguồn                                Master    Devstack
   =============================================== ========= ==================
.. note::
   **Lưu ý rằng tất cả các phương thức cài đặt đều yêu cầu một số kỹ năng nền tảng:**
    * Kiến thức cơ bản đối với hệ điều hành bạn đã chọn để cài đặt.
    * Biết sử dụng command line terminal để thực hiện các tác vụ.
    * Có khả năng chẩn đoán và giải quyết vấn đề xảy ra với phần mềm hệ thống.
