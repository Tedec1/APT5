#APT5 - 2

##Problem Statement
###Topic: Map, Pair

If you want to write a message anonymously, one way to do it is to cut out letters from headlines in a newspaper and paste them onto a blank piece of paper to form the message you want to write. Given several headlines that you have cut out, determine how many messages from a list you can write using the letters from the headlines. You should only consider each message by itself and not in conjunction with the others, see example 2.

Write the function how_many which takes as parameters a vector<string> headlinescontaining the headlines which you have cut out as well as a vector<string> messages with the messages you may want to write, and returns an int which is the total number of messages you can write.

Constraints
All letters that you cut out can be used both as upper or lower case in a message.
Spaces should be ignored in elements in both headlines and messages.
headlines will contain between 1 and 50 elements, inclusive.
messages will contain between 1 and 50 elements, inclusive.
The length of each element in headlines will be between 1 and 50 characters, inclusive.
The length of each element in messages will be between 1 and 50 characters, inclusive.
Each element in headlines will only contain the letters 'A'-'Z', 'a'-'z' and space.
Each element in messages will only contain the letters 'A'-'Z', 'a'-'z' and space.
Examples
headlines =
```c++
{"Earthquake in San Francisco",
 "Burglary at musuem in Sweden",
 "Poverty"}
```

messages =
```c++
{"Give me my money back",
"I am the best coder",
"TOPCODER"}
```

Returns: 2
In the first message we have three 'm's, but there are only two 'm's among the headlines (both in the word "museum"), so this message can't be written.

The second message can be written. Note that the first letter, 'I', only appears as lower case in the headlines, but that's allowed. The last message can also be written, so the method should return 2.

headlines =

        {"Programming is fun"}

messages =

        {"program","programmer","gaming","sing","NO FUN"}

Returns: 4
The messages "program", "gaming", "sing" and "NO FUN" can all be written but not "programmer" (no 'e's exist). The method should return 4.

headlines =

   {"abcdef","abcdef"}

messages =

   {"AaBbCc","aabbbcc","   ","FADE"}

Returns: 3
All messages except the second one can be written, because it contains three 'b's but there are only two 'b's available. Also note the message only containing spaces - such a message can of course always be written.

This problem statement is the exclusive and proprietary property of TopCoder, Inc. Any unauthorized use or reproduction of this information without the prior written consent of TopCoder, Inc. is strictly prohibited. © 2002, TopCoder, Inc. All rights reserved.

----------------------------------------------------------------------------------------------------------------------------------------
#APT 5 - 3
##Problem Statement
###Topic Queue

A sub-word is a possibly non-contiguous sub-sequence of characters in a string which is also recognizably a word.  Non-contiguous means the letters don't have to appear next to each other.  Sub-sequence means the letters are in the same order as found in the original string.

For example, the string sfpomrtq contains several sub-words: for, port, and or are some. Note that the sub-sequence property means that prom is not a valid sub-word, since the letters in prom do not appear in sequence in sfpomrtq.  The longest sub-word in sfpomrtq is sport.

In this problem you will be given a string and a vector of valid words. Your job is to find the length of the longest valid word that appears as a sub-word of the given string.  If no valid words are sub-words of the input, then you should return 0.

Notes and Constraints
words contains between 0 and 50 words.
input will be between 1 and 50 characters in length.
All strings contain only lowercase, alphabetic characters.
Examples

input = "sfpomrtq"
words = {"and", "is", "for", "hello"}

Returns: 3
In this dictionary, only "for" is a sub-word of the input.



input = "sfpomrtq"
words = {"or", "sport", "port", "for", "fort", "pot", "sot"}

Returns: 5
All of the words are sub-words of the input, but "sport" is the longest.



input = "supercalifragilisticexpialidocious"
words = {"sup", "super", "superficial", "supercilious", "superconductivity"}

Returns: 12
Here, "supercilious" is the longest valid word.




input = "xyz"
words = {"a", "b", "c", "d"}

Returns: 0
There are no valid sub-words.

starting code:

```c++
#include <vector>
#include <string>

int longest(string input, vector<string> &words) {
    // fill in code here
}
```


Creative Commons License
This work is copyright © Christopher Painter-Wakefield and is licensed under a Creative Commons Attribution-Share Alike 3.0 Unported License.
----------------------------------------------------------------------------------------------------------------------------------------
##Problem Statement
###Topic: Recursion

Circles Country is a country that contains several circular-shaped districts. Some districts may be situated inside other districts, but their borders do not intersect or touch. Qatam is a resident of Circles Country. When he travels between two locations, he always tries to cross the fewest number of district borders as possible because crossing borders is usually a laborious task.

Imagine Circles Country as an infinite plane. You are given vector<int> x and vector<int> y and vector<int> r, where (x[i],y[i]) are the coordinates of the ith district's center and r[i] is its radius.  There are n = x.size() circles altogether. You are additionally given coordinates x1,y1,x2,and y2. Qatam is currently at point (x1,y1) and he needs to get to point (x2,y2). Neither of these points lies on a district border. Return the minimal number of district borders he must cross to get to his destination.

Constraints
n will be between 1 and 50, inclusive.
x, y and r will each contain n elements.

Each element of x and y will be between -1000 and 1000, inclusive.

Each element of r will be between 1 and 1000, inclusive.

x1, y1, x2 and y2 will be between -1000 and 1000, inclusive.

No two circumferences will have common points.

The points (x1,y1) and (x2,y2) will not lie on any of the circumferences.

Examples

Input: {0},{0},{2},-5,1,5,1

Returns: 0




Input: {0,-6,6},{0,1,2},{2,2,2},-5,1,5,1

Returns: 2




Input: {1,-3,2,5,-4,12,12},{1,-1,2,5,5,1,1},{8,1,2,1,1,1,2},-5,1,12,1

Returns: 3




Input: {-3,2,2,0,-4,12,12,12},{-1,2,3,1,5,1,1,1},{1,3,1,7,1,1,2,3},2,3,13,2

Returns: 5




Input: {-107,-38,140,148,-198,172,-179,148,176,153,-56,-187},{175,-115,23,-2,-49,-151,-52,42,0,68,109,-174},{135,42,70,39,89,39,43,150,10,120,16,8},102,16,19,-108

Returns: 3

---

##Problem Statement
###Topic: Set

Southern China is suffering from a heavily snowy winter. The heavy snow even causes the closure of an important highway connecting southern and northern China. You've got several reports containing the start and end points of highway segments covered by heavy snow. Given those reports as two vector<int>, start_points and end_points , you are to return the total length of highway segments covered by snow. Note that the reported segments may overlap.

Constraints
start_points will contain between 1 and 50 elements, inclusive.
end_points will contain the same number of elements as start_points.
Each element of start_points and end_points will be between 0 and 10000, inclusive.
The i-th element of start_points will be smaller than the corresponding element in end_points.
Examples
start_points = {17,85,57}

end_points = {33,86,84}

Returns: 44
These segments don't overlap.


start_points = {45,100,125,10,15,35,30,9}

end_points = {46,200,175,20,25,45,40,10}

Returns: 132
There are 3 segments covered by snow: 9-25, 30-46 and 100-200.


start_points = {4387,711,2510,1001,4687,3400,5254,584,284,1423,3755,929,2154,5719,1326,2368,554}

end_points = {7890,5075,2600,6867,7860,9789,6422,5002,4180,7086,8615,9832,4169,7188,9975,8690,1423}

Returns: 9691
The snow covered segment is 284-9975.


start_points = {4906,5601,5087,1020,4362,2657,6257,5509,5107,5315,277,6801,2136,2921,5233,5082,497,8250,3956,5720}

end_points = {4930,9130,9366,2322,4687,4848,8856,6302,5496,5438,829,9053,4233,4119,9781,8034,3956,9939,4908,5928}

Returns: 9510
There are 2 segments covered by snow: 277-4930 and 5082-9939.


start_points = {51,807,943,4313,8319,3644,481,220,2161,448,465,1657,6290,22,6152,647,3185,4474,2168}

end_points = {1182,912,1832,7754,9557,7980,4144,3194,7129,5535,1172,2043,6437,7252,9508,4745,8313,8020,4017}

Returns: 9535


start_points = {8786,7391,201,4414,5822,5872,157,1832,7487,7518,2267,1763,3984,3102,7627,4099,524,1543,1022,3060}

end_points = {9905,7957,3625,6475,9314,9332,4370,8068,8295,8177,7772,2668,7191,8480,9211,4802,2625,1924,9970,4180}

Returns: 9813

---