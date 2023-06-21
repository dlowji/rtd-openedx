.. _xblock-introduction:

CÀI ĐẶT XBLOCK
==============

.. toctree:: :hidden:

Tổng quan về XBlock
-------------------
XBlock là một kiến trúc thành phần được thiết kế nhằm tạo điều kiện thuận lợi hơn cho việc tạo ra các trải nghiệm giáo dục trực tuyến mới. XBlock đã được phát triển bởi edX, một tổ chức tập trung vào giáo dục, nhưng công nghệ này có thể được sử dụng trong các ứng dụng web cần sử dụng nhiều thành phần độc lập và hiển thị các thành phần đó trên một trang web duy nhất.

Lập trình viên XBlock không cần tải xuống và chạy toàn bộ hệ thống phát triển edx- hoặc biết bất cứ điều gì về các công nghệ mà edX sử dụng để cung cấp XBlock runtime. Thay vào đó lập trình viên có thể thông qua Software Development Kit (XBlock SDK) và triển khai công việc của họ trên bất kỳ nền tảng nào tương thích với XBlocks.

Trong các ứng dụng giáo dục, XBlocks có thể được sử dụng để đại diện cho các bài toán cá nhân, văn bản và video định dạng web, mô phỏng tương tác và phòng thí nghiệm, hoặc trải nghiệm học tập cộng tác. Hơn nữa, XBlocks có thể được kết hợp, cho phép một nhà phát triển XBlock kiểm soát hiển thị của các XBlock khác để tạo thành các bài học, phần và toàn bộ khóa học.

Chúng ta có thể chọn từ các chức năng được phát triển bởi cộng đồng Open edX bằng cách cài đặt một XBlock trên phiên bản Open edX của mình. Bên cạnh đó, chúng ta cũng có thể tích hợp chức năng mới hoặc chức năng độc quyền để sử dụng trong XBlock runtimes bằng cách xây dựng và phát triển một XBlock mới.

XBlocks giống như các ứng dụng web thu nhỏ: chúng duy trì trạng thái trong một lớp lưu trữ, hiển thị thông qua các view và xử lý các hành động của người dùng thông qua các handler. XBlocks khác biệt so với các ứng dụng web ở chỗ chúng chỉ hiển thị một phần nhỏ trên một trang web hoàn chỉnh. Giống như thẻ HTML <div>, XBlocks có thể đại diện cho các thành phần nhỏ như một đoạn văn bản, một video hoặc một trường nhập lựa chọn đa lựa chọn, hoặc có thể lớn như một phần, một chương hoặc một khóa học toàn bộ.

Yêu cầu khi tìm hiểu XBlock
---------------------------
Bài viết này dành cho các lập trình viên muốn tiếp cận với XBlock. Người đọc nên nắm vũng kiến thức cơ bản của các công nghệ sau:
  * **Python**
  * **JavaScript**
  * **HTML và CSS**
  * **Môi trường ảo Python**
  * **Git**

Cài đặt các ràng buộc về phần mềm
---------------------------------
Để xây dựng một XBlock, chúng ta bắt buộc phải có các công cụ sau máy tính:
  * **Python**: Để chạy môi trường ảo và XBlock SDK, cũng như để xây dựng XBlock, lập trình viên phải `cài đặt Python có phiên bản >= 3.8 <https://www.python.org/downloads/>`_ trên máy tính.
  * **Git**: Các edX repository, bao gồm XBlock và XBlock SDK hiện nay được lưu trữ phổ biến trên GitHub. Chúng tôi khuyến nghị nên sử dụng Git nhằm dễ dàng kiểm soát mã nguồn trong quá trình phát triển XBlock, thuận tiện cho việc triển khai ở tương lai. Nếu chưa cài đặt Git hoặc chưa được làm quen với công cụ này, người đọc có thể tham khảo thêm `ở đây <https://docs.github.com/en/get-started/quickstart/set-up-git>`_. 
  * **Môi trường ảo Python**: Về thông tin cơ bản cũng như lợi ích khi sử dụng môi trường ảo Python, chúng tôi đã đề cập ở bài viết :ref:`Cài đặt hệ thống Open edX bằng Tutor <tutor-settingup-requirement>`. Độc giả có thể tham khảo thêm :ref:`cách cài đặt và sử dụng môi trường ảo Anaconda <anaconda-settingup>`.

Các bước dựng XBock SDK
-----------------------
Trước khi đi tiếp ở phần nãy, đảo bảo rằng đã làm quen và cài đặt đầy đủ  trên máy tính các công nghệ trong phần điều kiện tiên quyết khi xây dựng XBlock.

Bây giờ thì chúng ta đã sẵn sàng để dựng XBlock SDK trên môi trường ảo, theo các bước sau:

Đầu tiên, tiến hành tạo một thư mục mới. Trong thư mục này sẽ lưu trữ tất cả mọi thứ chúng ta sẽ làm việc liên quan đến XBlock, gồm có môi trường ảo, XBlock SDK và các XBlock chúng ta sẽ phát triển.

Trong bài viết này, chúng tôi sẽ tạo thư mục mới có tên là "xblock_development" bằng câu lệnh sau trong command promt:

.. code-block:: console
  
    (base) User>mkdir xblock_development

Sau đó tiếp tục di chuyển đến thư mục vừa tạo:

.. code-block:: console
  
    (base) User>cd xblock_development

Từ giờ mọi quá trình phát triển XBlock sẽ chỉ diễn ra bên trong thư mục này.

Tạo môi trường có tên "venv" đồng thời cài đặt Python phiên bản 3.8:

.. code-block:: console
  
    (base) User\xblock_development>conda create -n venv python=3.8

Kích hoạt môi trường vừa được tạo trước đó:

.. code-block:: console
  
    (venv) User\xblock_development>conda activate venv

Clone XBlock SDK
----------------
Như chúng tôi đã đề cập ở phía trên, XBlock SDK là một ứng dụng Python được sử dụng để hỗ trợ xây dựng các XBlock mới. XBlock SDK bao gồm 3 thành phần chính:
  * **XBlock Creation Tool**: Mang vai trò dựng nên "bộ xương" khi một XBlock mới được tạo ra. Bộ xương ở đây chính là cấu trúc cơ bản hoặc bản mẫu ban đầu. Bên trong bản mẫu là một tập hợp các tập tin (HTML, CSS, Python, ...) và thư mục được tạo tự động để lập trình viên có thể triển khai chức năng và giao diện của XBlock một cách dễ dàng, nhanh chóng.
  * **XBlock Runtime**: Cung cấp khả năng hiển thị và tương tác nhằm mục đích theo dõi và kiểm thử XBlock chúng ta đang xây dựng. Bên cạnh đó, ứng dụng còn cho phép lập trình viên kiểm tra tính năng, giao diện phía người dùng trong môi trường tương tự khi ở trang web thực tế.
  * **Sample XBlocks**: Đây là những XBlock mẫu, có chức năng và giao diện dành cho người dùng. Lập trình viên có thể tham khảo mã nguồn bên trong để có cái nhìn tổng quan hơn về cách xây dụng và triển khai XBlock.

Sau khi tạo và kích hoạt môi trường ảo thành công, thực hiện các bước sau để tiến hành clone XBlock SDK, và cài đặt các thư viện, các package theo yêu cầu.

Clone XBlock SDK repository từ GitHub qua lệnh git:

.. code-block:: console
  
    (venv) User\xblock_development >git clone https://github.com/edx/xblock-sdk.git

Tiếp theo, tạo thư mực "var":

.. code-block:: console
  
    (venv) User\xblock_development >mkdir var

Truy cập thư mục xblock-sdk:

.. code-block:: console
  
     (venv) User\xblock_development >cd xblock-sdk

Cài đặt các thư viện, package theo yêu cầu:

.. code-block:: console
  
    (venv) User\xblock_development\xblock-sdk> pip install -qr requirements/dev.txt --exists-action w

Hoặc

.. code-block:: console
  
    (venv) User\xblock_development\xblock-sdk> make install

Cuối cùng, trở về thư mục gốc bằng lệnh:

.. code-block:: console
  
    cd ..

Tạo XBlock đầu tiên
--------------------
Di chuyển đến thực mục xblock_development, chạy tập tin "workbench-make-xblock" bằng lệnh python:

.. code-block:: python

	  (venv) User\xblock_development>python xblock-sdk/bin/workbench-make-xblock

Sau khi chạy, cửa sổ Command yêu cầu chúng ta cung cấp các thông tin cấu hình cho XBlock: 

	Short name: myxblock

	Class name: MyXBlock

.. note::

    Short name nên chỉ gồm một từ duy nhất, tất cả ký tự đều viết thường. Lấy một ví dụ, trong trường hợp muốn tạo Question Generation XBlock, chúng ta có thể đặt là “questgen”.

    Class name là tên class hợp lệ trong ngôn ngữ Python và nên kết thúc bằng “XBlock”, cùng ví dụ ở trên, lúc này ta có thể đặt là “QuestGenXBlock”.
    
    Sau khi nhập xong 2 thông tin trên, một thư mục mới được tạo ra nằm bên trong thư mục “xblock_development”. Thư mục mới này chứa các thư mục con và các tập tin cho XBlock vừa tạo.
    
    Trong quá trình nhập thông tin, có thể bấm tổ hợp phím “Ctrl + C” để dừng và quay trở lại. Trong trường hợp không ưng ý sau khi đã được tạo, chúng ta có thể tiến hành xóa chính thư mục đó.

Sau khi tạo mới XBlock, chúng ta phải cài đặt nó vào trong XBlock SDK.

Dùng lệnh pip để cài đặt myxblock

.. code-block:: console

	  (venv) User\xblock_development>pip install -e myxblock

Khởi tạo SQLite Database
------------------------
Chạy lệnh migrate để tạo database và các bảng:

.. code-block:: console

	  (venv) User\xblock_development>python xblock-sdk/manage.py migrate

Chạy XBlock SDK server
----------------------

.. code-block:: console

	  (venv) User\xblock_development>python xblock-sdk/manage.py runserver

Nếu không chỉ định cổng, server XBlock SDK mặc định sẽ sử dụng cổng 8000. Chỉ định port trong câu lệnh runserver nếu muốn sử dụng một cổng khác.

Để kiểm tra xem XBlock SDk có chạy thành công hay không. Mở trình duyệt web lên và truy cập  http://localhost:8000. Nếu các bạn thấy giao diện sau thì Chúc mừng, các bạn đã chạy thành công.

Nhúng XBlock Audio vào XBlock SDK
---------------------------------
Clone AudioXBlock từ github về bằng lệnh git clone:
.. code-block:: console

    (venv) User\xblock_development>git clone https://github.com/pmitros/AudioXBlock 

Dùng pip install để cài audio xblock vào XBlock SDK:

.. code-block:: console

    (venv) User\xblock_development>pip install -e AudioXBlock


