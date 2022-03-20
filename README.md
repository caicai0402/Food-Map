# Food-Map

## 1、 程式理念與目的
 此程式主要目的在幫助吃飯時陷入選擇障礙的人們。使用者透過輸入偏好的食物類型以及交通方式，基於這些條件，我們程式將為使用者挑選出評價最高的餐廳，並提供餐廳評論、餐廳附近停車場、地圖...等額外資訊。
 
## 2、 操作方式與功能說明
執行程式碼後，在使用者必須在介面上先選擇食物類型、交通方式以及可接受的交通時間，按下確定鍵，程式將根據選擇條件挑出Google評價最高之餐廳。左方店家資訊顯示店名、地址、評價以及部分Google評論，若交通方式選擇汽車，右方交通資訊將顯示餐廳半徑150m內有哪些停車場。 
 店家資訊與交通資訊出現後，下方會出現”查看地圖”之按鍵，點下後會執行folium，並叫出另一個視窗，為包含使用者位置、餐廳位置、停車場位置之地圖 (使用者位置:藍色標記、餐廳:紅色標記、停車場:綠色標記)
 
## 3、 程式說明
### 1.資料來源  
 我們申請 Google Maps Api金鑰，在程式輸入使用者位置經緯度、搜尋半徑、搜尋關鍵字，便可得到範圍內Google maps的餐廳資訊以及停車場資訊。
### 2.資料篩選過程
 使用者所在經緯度，會以易哲助教先前提供的使用者定位程式定位出來，搜尋半徑將根據介面上選擇之交通方式與時間決定。我們定義各交通方式的速度分別為: 走路1.5km/hr、腳踏車4.5km/hr、機車25km/hr（根據生活經驗）、汽車25km/hr（根據生活經驗和交通路況），最後根據選擇的餐廳食物類型，篩出該類型Google評價最高之店家。由於有位移跟路徑的差別因此我們將汽機車的速度設小一點，以調整路徑和直線距離的不同所形成的誤差
### 3.畫面呈現
使用tkinter製作使用者介面，製作商家種類、交通工具、交通時間等選單，並製作表格呈現所搜尋的商家資訊如：評價、名稱、地點等。以Folium顯示搜尋結果的地圖，並在地圖上標示使用者位置與店家位置，以利判讀。
### 4.問題待解決
​版面在不同的電腦可能失真，問題超出能力所及。地圖呈現也因不同的電腦決定能否執行，通常在mac電腦不會成功。在介面評論處，因tkinter不支援emoji文字，將導致某些評論無法順利呈現。在GUI介面的使用通常最多只能點選兩次，否則程式會超過負荷，這與程式優化有關，將在之後的版本裡解決。
