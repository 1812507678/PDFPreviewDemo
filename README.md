pdf预览demo

参考GitHub上H5加载PDF的项目：https://github.com/gjTool/pdfh5

接入步骤：
    1.添加权限
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
        <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    2.在布局文件中加入一个webView
        <WebView
                android:id="@+id/webview"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:layout_weight="1" />
    3.在Activity加载PDF文件链接，有两种方案
        ①把加载文件的静态文件拷贝到assets目录下
            String url = "https://www.gjtool.cn/pdfh5/git.pdf";  //测试PDF文件
            mWebView.loadUrl(String.format("file:///android_asset/pdfload/pdf.html?file=%s",url));  //通过本地资源请求
        ②把加载文件的静态文件放到服务器上，通过加载服务器的静态资源访问
            String url = "https://www.gjtool.cn/pdfh5/git.pdf";  //测试PDF文件
            mWebView.loadUrl("http://localhost/webProject/pdfload/pdf.html?file=%s",url);  //通过本地资源请求
            

如遇到问题可以加我QQ或者发邮件咨询，QQ：1812507678，邮箱：1812507678@qq.com