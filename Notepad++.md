Máy quá yếu để code c++ nên đành xài nodepad++

[Link cài gcc c++11 ở đây](https://www.mediafire.com/file/rpl5n7224bkpje1/gcc-11.1.0-no-debug.7z/file)

Check g++: Run cmd - gõ ``` g++ --version ```

![image](https://github.com/VanHoang110802/Tricks_IDEs/assets/108053955/0c6ea01b-3ef4-4214-8503-178ff9de92a8)

Lệnh để setup compiler:
```
npp_save
cd "$(CURRENT_DIRECTORY)" 
g++ "$(FILE_NAME)" -o $(NAME_PART) -static-libgcc -static-libstdc++
$(NAME_PART).exe
```

> Chương trình sort tăng dần:

![image](https://github.com/VanHoang110802/Tricks_IDEs/assets/108053955/7d160402-a21a-4fa7-a8ff-bc8e59ccf239)
