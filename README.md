# Pic16F877A_C_StudyProject1
Pic16F877A heart led controling with IC 595
- How 74HC595 works:
First a small example of to regist data on IC:

void registData1(){
</br>&emsp;SH_PIN = 0;
</br>&emsp;DS_PIN = 0;
</br>&emsp;SH_PIN = 1;
</br>}

</br>First pin on 595 will be low (Q1 = 0)
</br>If the function like this

void registData2(){
</br>&emsp;SH_PIN = 0;
</br>&emsp;DS_PIN = 1;
</br>&emsp;SH_PIN = 1;
</br>}

</br>First pin on 595 will be high (Q1 = 1)
</br>When we want output the regist pin the pin ST first must be low.

void registData1(){
</br>&emsp;ST_PIN = 0;
</br>&emsp;SH_PIN = 0;
</br>&emsp;DS_PIN = 0;
</br>&emsp;SH_PIN = 1;
</br>&emsp;ST_PIN = 1;
</br>}

</br>at a time first pin on 595 will be immediatly low (Q1 = 0)
</br>and output high on pin Q1 = 1 as well

void registData1(){
</br>&emsp;ST_PIN = 0;
</br>&emsp;SH_PIN = 0;
</br>&emsp;DS_PIN = 1;
</br>&emsp;SH_PIN = 1;
</br>&emsp;ST_PIN = 1;
</br>}

==>
</br>DS pin : data pin decided the pin on 595 will be low or high
</br>SH pin : clock pin, will catch the data at that moment.
</br>ST pin : latch pin, will use when we want output the data, just turn off before regist the data then turn on, the data will output on pin
