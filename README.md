# Assignment-Practice
計算機概論作業跟計算機實習作業
//A09
#include <iostream>
using namespace std;
int main(){
    int round;
    cin >> round;
    for (int i=1;i<=round;i++){ // 不用加冒號
        int pipes;
        cin >> pipes;
        int climb_times = 0,descent_times = 0,maintain_times = 0;
        int climb_distance = 0,descent_distance = 0,maintain_distance = 0;
        int OriginalX = 0,OriginalY= 0;
        cin >> OriginalX >> OriginalY;
        int CurrentX = 0,CurrentY= 0;
        cout << "---CASE"<<i<<"---"<< endl; //endl是換行的意思
        for (int t=0;t<pipes;t++){ //意思是設一個t=0只要小於pipes就做一次迴圈並且做下一次迴圈時t加一
            cin >> CurrentX >> CurrentY;
            if (CurrentY  > OriginalY- CurrentX + OriginalX + 1){
                climb_times = climb_times + 1;
                climb_distance = CurrentY - OriginalY + CurrentX - OriginalX - 1 ;
                OriginalX = CurrentX;//把現在的值變成下一次比較的起始值
                OriginalY = CurrentY;
                cout << "Climb:"<< climb_distance<<endl;
            }
            else if (CurrentY == OriginalY - CurrentX + OriginalX + 1){
                maintain_times = maintain_times + 1;
                maintain_distance = CurrentY - OriginalY + CurrentX - OriginalX - 1 ;
                OriginalX = CurrentX;
                OriginalY = CurrentY;
                cout << "Maintain "<<endl;
            }
            else if (CurrentY  < OriginalY- CurrentX + OriginalX + 1){
                descent_times = descent_times + 1;
                descent_distance = OriginalY- CurrentX + OriginalX + 1 - CurrentY;
                OriginalX = CurrentX;
                OriginalY = CurrentY;
                cout << "Descent:"<< descent_distance<<endl;
            }
        }
        
        
        
        
    }
    return 0;
}
