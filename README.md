# IPRangeReduce
CSVで与えられたIPアドレスのRangeをすべて/32(または/128)のアドレスに分解してCSVに出力するスクリプト


# Demo
```
$ cat import.csv
192.168.1.1, 192.168.1.5
172.27.2.2, 172.27.2.4

$ python3 rangereduce.py

$ cat output.csv
192.168.1.1
192.168.1.2
192.168.1.3
192.168.1.4
192.168.1.5
172.27.2.2
172.27.2.3
172.27.2.4
```

# Requirement
* Python 3.6
* [netaddr 0.7.19](https://github.com/drkjam/netaddr)
    ```
    $ python3 -m pip install netaddr
    ```

# Example
1. 変換したいIPアドレスの範囲を記載したCSVファイルを用意
    * 192.168.1.1 ~ 192.168.1.127 と 192.168.2.1 ～ 192.168.2.127 までのIPアドレスを全て出力したい場合
        ```
        192.168.1.1, 192.168.1.127
        192.168.2.1, 192.168.2.127
        ```
    

1. `rangereduce.py`の下記変数にInputとOutputに用いるファイルのpathを記載
    ```
    # Import CSV File Path
    import_file_path = ''
    # Output CSV File Path
    output_file_path = ''
    ```

1. `rangereduce.py`を実行
    ```
    $ python3 rangereduce.py
    ```
