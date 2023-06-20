================
Cài đặt Anaconda
================

Chúng tôi khuyến khích nên cài đặt Tutor bằng việc sử dụng môi trường ảo Python. Một môi trường ảo là công cụ cho phép chúng ta lưu trữ các dependencies theo yêu cầu của các dự án khác nhau ở nhiều nơi riêng biệt.

Bằng việc sử dụng môi trường ảo, chúng ta có thể cài đặt các gói và thư viện cần thiết mà không gây xung đột với các phiên bản và môi trường Python khác trên hệ thống. Điều này giúp đảm bảo rằng Open edX và các thành phần liên quan của phần mềm sẽ hoạt động đúng cách và không ảnh hưởng đến các ứng dụng khác trên máy tính. Bên cạnh đó, môi trường ảo hỗ trợ nhiều nền tảng khác nahu bao gồm Windows, macOS và Linux. Điều này giúp đơn giản hóa quá trình cài đặi và hủy cài đặt Open edX trên các hệ điều hành khác nhau mà không cần lo lắng về sự tương thích.

Trong chuỗi bài viết về Open edX này, chúng tôi sẽ sử dụng Anaconda. Người đọc có thể tìm hiểu thêm về Anaconda `ở đây <https://www.anaconda.com/>`_.

Sau khi cài đặt, bước tiếp theo chúng ta cần tạo một môi trường ảo mới bằng cách mở Anaconda Prompt.

Để tạo một môi trường ảo mới có tên là py35, đồng thời cài đặt python phiên bản 3.5, ta sử dụng câu lệnh:

.. code-block:: bash

    conda create –name py35 python=3.5

Nếu muốn tìm hiểu thêm về các câu lệnh được sử dụng trong Anaconda, người đọc có thể tham khảo `ở đây <https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf>`_.
Sau khi đã tạo mới môi trường ảo thành công, để có thể sử dụng nó ta cần kích hoạt bằng câu lệnh:

.. code-block:: bash

    conda activate py35

.. note:: 
    py35 ở đây chính là tên của môi trường mà chúng ta đã tạo ở trên.

Khi môi trường đã được kích hoạt, Anaconda Promt sẽ hiển thị tên của môi trường vừa được kích hoạt nằm trong cặp ngoặc đơn.
