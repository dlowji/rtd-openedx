.. _introduce-alpha:

===========================
Cài đặt Open edX bằng Tutor
===========================

.. contents::
   :local:

.. toctree::

   Cài đặt Anaconda :ref:`anaconda`
   Cài đặt Tutor :ref:`tutor`


Trong phạm vi bài viết này, chúng tôi sẽ xây dựng server Open edX bằng `Tutor <https://docs.tutor.overhang.io/>`_. `Tutor <https://docs.tutor.overhang.io/>`_ là bản phân phối hay phần mềm từ Open edX phát triển cho người dùng cuối dựa trên nền Docker, cho cả môi trường production và phát triển cục bộ trên máy tính của chúng ta. Mục tiêu của `Tutor <https://docs.tutor.overhang.io/>`_ là giúp dễ dàng triển khai, tùy chỉnh, nâng cấp và mở rộng Open edX. Tutor đáng tin cậy, nhanh chóng, có thể mở rộng và phương thức này đã được sử dụng để triển khai hàng trăm nền tảng Open edX trên khắp thế giới.

Một số tính năng, đặc điểm nổi bật của Tutor mà chúng tôi đã cân nhắc để sử dụng phương thức này cho việc cài đặt Open edX:
 * 100% `mã nguồn mở <https://github.com/overhangio/tutor>`_.
 * Chạy hoàn toàn trên `Docker <https://www.docker.com/>`_
 * Được cả thế giới biết đến với việc cài đặt và nâng cấp chỉ bằng 1 cú nhấp chuột.
 * Kiến trúc có thể mở rộng với các `plugins <https://docs.tutor.overhang.io/plugins/index.html>`_.
 * Có thể hoạt động tương thích với `Kubernetes <https://docs.tutor.overhang.io/k8s.html>`_.
