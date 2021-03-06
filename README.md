# setup_manual
Team5 セットアップマニュアル

---
## CRANE-X7のROSパッケージをインストール

```
  $ cd ~/catkin_ws/src
  $ git clone https://github.com/RobotDesign3-Team5/crane_x7_ros.git
  $ rosdep install -r -y --from-paths --ignore-src crane_x7_ros
```

---
## 実機を使う場合
- ### モデルの配置
  実機で動作確認を行う場合，以下の図のようにモデルを配置してください．
  <img src="https://user-images.githubusercontent.com/53966271/98900657-90ceee00-24f5-11eb-842a-0d17a6daa277.jpg" width="640px">
  <img src="https://user-images.githubusercontent.com/53966390/98886454-77b74480-24d7-11eb-9144-1a447d2191e7.png" width="640px">
- ### 実機の動かし方
  - CRANE-X7をUSB接続し，下記のコマンドでアクセス権を変更してください．
    ``` 
    $ sudo chmod 666 /dev/ttyUSB0
    ```
  - 動作確認をする場合は下記のコマンドを実行してから，プログラムを実行してください．
    ```
    $ roslaunch crane_x7_bringup demo.launch fake_execution:=false
    ```

---
## gazeboを使用する場合
  - ### gazeboモデルのインストール
    - #### 方法① - コマンド
      下記のコマンドでモデルをクローンしてください．
      ```
      $ cd ~/.gazebo/models
      $ git clone https://github.com/RobotDesign3-Team5/asstseal_model.git
      $ git clone https://github.com/RobotDesign3-Team5/storage_model.git
      $ git clone https://github.com/RobotDesign3-Team5/inkpad_model.git
      $ git clone https://github.com/RobotDesign3-Team5/sealmat_model.git
      $ git clone https://github.com/RobotDesign3-Team5/TissuePaper_model.git
      $ git clone https://github.com/RobotDesign3-Team5/GlueStick_model.git
      $ git clone https://github.com/RobotDesign3-Team5/eraser_model.git
      $ git clone https://github.com/RobotDesign3-Team5/battery_model.git
      ```
    - #### 方法② - bash
      下記の方法でbashを実行してください．
      ```
      $ cd ~/setup_manual
      $ chmod +x gazebo.bash
      $ ./gazebo.bash
      ```
  - ### gazebo起動方法
    下記のコマンドでgazeboを起動してください．
    ```
    $ roslaunch crane_x7_gazebo crane_x7_with_table.launch
    ```

---
## プログラム
  - ### 実行方法
    下記のコマンドでプログラムを実行してください．
    ```
    $ rosrun crane_x7_examples robotdesign3_team5.py
    ```

  - ### 一連の流れ

    1.  書類に目を通す
    2.  はんこを探す
    3.  はんこを持ち朱肉につける
    4.  インクが付いたか確認する
    5.  書類に捺印する
    6.  ティッシュペーパーではんこを拭く

  - ### 保存ディレクトリ
    `~/catkin_ws/src/crane_x7_ros/crane_x7_examples/scripts`
  
    上記ディレクトリ内の **robotdesign3_team5.py** がプログラムコードになります.

---
