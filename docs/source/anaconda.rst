.. _anaconda:

Sử dụng Anaconda
================
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
