

## *实验过程*
	### 3.4 Writing webget ，编写get_url()函数
	   根据实验指导，仔细看看 Adress类 ，还有TCPSocket类的成员函数接口即可完成
	    ```c++
	     void get_URL( const string& host, const string& path ){
      cerr << "Function called: get_URL(" << host << ", " << path << ")\n";
      Address addr(host, "http");
      TCPSocket socket;
      socket.connect(addr);
      const string content("GET " + path + " HTTP/1.1\r\n"
                    + "Host: " + host + "\r\n"
                    + "Connection: close\r\n\r\n"); 
      socket.write(content);
      string res;
      while (!socket.eof()){
        socket.read(res);
        cout<<res;
      }
      socket.close();
      cerr << "Warning: get_URL() has not been implemented yet.\n";
    }```



    ### 4 An in-memory reliable byte stream
      



