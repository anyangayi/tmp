# tmp

#include<iostream>
#include<string>
#include<vector>
using namespace std;

string s1 = "小浣熊、袋鼠、狐狸、猎豹、恐龙、电鳗、蚯蚓、蛾子、大猩猩、美人鱼、大象、海豚、老鼠、蟑螂、蝴蝶、北极熊、长颈鹿、蝎子、金鱼、蜈蚣、孔雀、大灰狼、青蛙、蜻蜓、鸵鸟、山羊、蜗牛、萤火虫、猫头鹰、刺猬、燕子、虾、马蜂、蚂蚁、小白兔、金钱豹";
string s2 = "北研所、Q14、数通、网络、数据中心、万物互联、拓扑、实习生、编程、debug、C++、Docker、开发、测试、刷题、力扣";
string s3 = "空调、面粉、酱油、大米、啤酒、洗衣机、音响、饮水机、围裙、军棋、跳棋、餐巾纸、电梯、火锅、熨斗、雨衣、香皂、皮鞋、红领巾、雨鞋、水笼头、日光灯、茶叶、围巾、打印机、日历";
string s4 = "拔苗助长、画蛇添足、对牛弹琴、如鱼得水、画龙点睛、鸡飞狗跳、掩耳盗铃、对牛弹琴、藕断丝连、暴跳如雷、狼吞虎咽、见钱眼开、贼眉鼠眼、牛头马面、虎头蛇尾、兔死狐悲、龙腾虎跃、狗急跳墙、摇头晃脑、撒腿就跑、垂头丧气、昂首挺胸、手舞足蹈、张牙舞爪、眉开眼笑、目瞪口呆、呆若木鸡、哭笑不得、捧腹大笑、指手划脚、蹑手蹑脚、废寝忘食、闻鸡起舞、守株待兔、掩耳盗铃、盲人摸象、狼吞虎咽、抓耳挠腮、争先恐后、一刀两断、坐井观天、快马加鞭";

vector<string> func(string s){
    vector<string> ans;
    string pattern = "、";
    string strs = s + pattern;
    int pos = strs.find(pattern);
    int size = strs.size();
    while(pos != string::npos){
        string x = strs.substr(0, pos);
        ans.emplace_back(x);
        strs = strs.substr(pos+1, size);
        pos = strs.find(pattern);
    }
    return ans;
}

int main(){
    vector<string> nums1 = func(s1);
    vector<string> nums2 = func(s2);
    vector<string> nums3 = func(s3);
    vector<string> nums4 = func(s4);
    int key;
    while(key != -1){
        cout << "请输入组别(1-4)：";
        cin >> key;
        if(key == 1){
            int size = nums1.size();
            int index = rand() % size;
            cout << "请绘画：" << nums1[index] << endl;
        }
        else if(key == 2){
            int size = nums2.size();
            int index = rand() % size;
            cout << "请绘画：" << nums2[index] << endl;
        }
        else if(key == 3){
            int size = nums3.size();
            int index = rand() % size;
            cout << "请绘画：" << nums3[index] << endl;
        }
        else if(key == 4){
            int size = nums4.size();
            int index = rand() % size;
            cout << "请绘画：" << nums4[index] << endl;
        }
        else continue;
    }
    return 0;
}
