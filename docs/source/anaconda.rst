.. _anaconda-settingup:

Cài đặt và sử dụng Anaconda
===========================
Bước đầu tiên, hãy `cài đặt Anaconda <https://www.anaconda.com/download/>`_.

Sau khi cài đặt thành công, bước tiếp theo chúng ta cần tạo một môi trường ảo mới bằng cách mở Anaconda Prompt (hoặc bên trong terminal trên Linux/macOS).

* **Windows**: Mở Start, tìm kiếm và chọn Anaconda Promt.
* **macOS**: Mở Launchpad, sau đó mở terminal hoặc iTerm.
* **Linux-CentOS**: Mở Applications - System Tools - terminal.
* **Linux-Ubuntu**: Mở Dash bằng cách click vào biểu tượng Ubuntu ở góc trên bên trái màn hình, sau đó nhập từ khóa "terminal".

Tạo mới môi trường ảo
---------------------
Để tạo một môi trường ảo mới có tên là py35, đồng thời cài đặt python phiên bản 3.5, ta sử dụng câu lệnh:

.. code-block:: console

    conda create –name py35 python=3.5

Nếu muốn tìm hiểu thêm về các câu lệnh được sử dụng trong Anaconda, người đọc có thể tham khảo `ở đây <https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf>`_.

Kích hoạt môi trường ảo
------------------------
Sau khi đã tạo mới thành công, để có thể sử dụng môi trường ảo này ta cần kích hoạt bằng câu lệnh:

.. code-block:: console

    conda activate py35

.. note:: 
    py35 ở đây chính là tên của môi trường mà chúng ta đã tạo ở trên.

    Khi môi trường đã được kích hoạt, Anaconda Promt sẽ hiển thị tên của môi trường vừa được kích hoạt nằm trong cặp ngoặc đơn.
