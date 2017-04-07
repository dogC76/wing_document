# 天翼畫面API對照表



---
# 背景呼叫



`AU074` app_user_attendance/add_gps_track **會一直去呼叫**

`SC031` system_config/get_version **一直去呼叫**


---
#  登入畫面

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%99%BB%E5%85%A5-02.png" width = "300" height = "500" alt="登入畫面" align=center />    
 


`SC031` system_config/get_version `android`

---

##  登入

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%99%BB%E5%85%A5.png" width = "300" height = "500" alt="登入" align=center />    

`AU001` app_user/login

`AU051` app_user/get_groups **怪 android會call兩次**

`AU094` app_user_notify/get_count_by_user  


`PS001` push/save_device_token  


`AG031` app_group/get_managers_by_user

`AG017` app_group/get_group_item

`AG010` app_group/get_users_by_enterprise_group `android`

`AG032` app_group/get_allgroups_by_enterprise `android`

`AG015` app_group/get_groups_by_enterprise  `ios`  


`SR003` schedule/get_targets_by_enterprise `ios`

`SR061` schedule/get_alert_by_number


##  忘記密碼

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E5%BF%98%E8%A8%98%E5%AF%86%E7%A2%BC.png" width = "300" height = "500" alt="忘記密碼" align=center />    
 
`AU012` app_user/cellphone_check

`AU021` app_user/active_send_sms

##  填寫驗證碼

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E5%A1%AB%E5%AF%AB%E9%A9%97%E8%AD%89%E7%A2%BC.png" width = "300" height = "500" alt="填寫驗證碼" align=center />    
 
`AU022` app_user/active_verify_sms

**驗證碼填寫過要call甚麼api要確認**

##  忘記密碼-送出

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E5%BF%98%E8%A8%98%E5%AF%86%E7%A2%BC_%E9%80%81%E5%87%BA.png" width = "300" height = "500" alt="忘記密碼-送出" align=center />    
 
`AU041` app_user/update_secret


##  新用戶註冊

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E7%94%A8%E6%88%B6%E8%A8%BB%E5%86%8A.png" width = "300" height = "500" alt="新用戶註冊" align=center />    
 
`AU011` app_user/cellphone_signup 


`SC035` system_config/get_config `android`  
(call了兩次分別帶tos跟privacy兩個參數)

---

#  首頁

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%A6%96%E9%A0%81.png" width = "300" height = "500" alt="首頁" align=center />    
 
`AG017` app_group/get_group_item 


`AU094` app_user_notify/get_count_by_user


`AU051` app_user/get_groups `android`

#  首頁_報表

 <img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%A6%96%E9%A0%81_%E5%A0%B1%E8%A1%A8.png" width = "300" height = "500" alt="首頁_報表" align=center />    
 
`SR101` schedule/get_user_type2_report


#  首頁_任務

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%A6%96%E9%A0%81_%E4%BB%BB%E5%8B%99.png" width = "300" height = "500" alt="首頁_任務" align=center />   

`SR001` schedule/get_by_days  **ios每點一天會call一次API，android只會call一次**

###  新增任務

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E5%A2%9E%E4%BB%BB%E5%8B%99.png" width = "300" height = "500" alt="新增任務" align=center />    

**檢查android**
`SR011` schedule/update_item

###  點擊任務進入任務詳細資訊

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%BB%9E%E6%93%8A%E4%BB%BB%E5%8B%99%E9%80%B2%E5%85%A5%E4%BB%BB%E5%8B%99%E8%A9%B3%E7%B4%B0%E8%B3%87%E8%A8%8A.png" width = "300" height = "500" alt="點擊任務進入任務詳細資訊" align=center />  

`SR002` schedule/get_item_by_id

###  匯報任務

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E5%8C%AF%E5%A0%B1%E4%BB%BB%E5%8B%99.png" width = "300" height = "500" alt="匯報任務" align=center />  

`SR082` schedule_mission/update_report  


`SR017` schedule/upload_image 如果有照片

###  群組任務_篩選

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%BE%A4%E7%B5%84%E4%BB%BB%E5%8B%99_%E7%AF%A9%E9%81%B8.png" width = "300" height = "500" alt="群組任務_篩選" align=center />  

`AG009` app_group/get_users_by_main_group `android` (會call多次)  

`AG010` app_group/get_users_by_enterprise_group

`AG007` app_group/get_managers_by_group_id

`AG015` app_group/get_groups_by_enterprise  `ios`

`AU066` app_user_attendance/get_attendance_flow_by_manager `ios`

###  群組任務_篩選 選擇成員

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%BE%A4%E7%B5%84%E4%BB%BB%E5%8B%99_%E9%81%B8%E6%93%87%E6%88%90%E5%93%A1.png" width = "300" height = "500" alt="群組任務_篩選 選擇成員" align=center />  

`SR001` schedule/get_by_days

---

#  首頁_拜訪

###  拜訪列表

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%BE%A4%E7%B5%84%E5%88%97%E8%A1%A8.png" width = "300" height = "500" alt="拜訪列表" align=center />  

`SR001` schedule/get_by_days

###  點擊拜訪進入拜訪詳細資訊



`SR002` schedule/get_item_by_id

`SR005` schedule/get_feedback_by_feedback_id 有回饋資料時

`SR013` schedule/set_status_done `ios` 按下開始或結束拜訪

`SR007` schedule/get_target_by_enterprise `ios` 按下開始拜訪


`CT013` contacter/get_company_by_id `android` 需確認是否選的公司不同

`CT004` contacter/get_company_near_by_gps `android` 需確認是否選的公司不同

###  結束拜訪

`SR013` schedule/set_status_done 

###  暫存

`SR013` schedule/set_status_done `android`

`SR021` schedule/update_feedback

`SR002` schedule/get_item_by_id

`SR005` schedule/get_feedback_by_feedback_id


###  按下記錄此次拜訪


`SR021` schedule/update_feedback

`SR013` schedule/set_status_done

`SR022` schedule/upload_feedback_image

`SR002` schedule/get_item_by_id 重新刷新頁面

`SR005` schedule/get_feedback_by_feedback_id 重新刷新頁面

###  記錄且下次拜訪

`SR021` schedule/update_feedback

`SR013` schedule/set_status_done

`SR002` schedule/get_item_by_id `android`

`SR003` schedule/get_targets_by_enterprise `android`

###  編輯拜訪
**編輯拜訪未完**

`SR011` schedule/update_item

`SR056` schedule/set_record_id `ios`

**指派人員未完**

`ios`
`AG010` app_group/get_users_by_enterprise_group 會call多次

`AG015` app_group/get_groups_by_enterprise

`AG007` app_group/get_managers_by_group_id 會call多次

`AG006` app_group/get_users 會call多次


`AU066` app_user_attendance/get_attendance_flow_by_manager

###  聯絡人詳細資訊


`CT012` contacter/get_person_by_company_id

`CT013` contacter/get_company_by_id

---
###  新增拜訪


`CT003` contacter/get_company_by_user `android`


`SR003` schedule/get_targets_by_enterprise `android`

###  新增拜訪_選擇成員

`AG010` app_group/get_users_by_enterprise_group

`AG009` app_group/get_users_by_main_group `android` 會call多次api

`AG015` app_group/get_groups_by_enterprise `ios`

`G006` app_group/get_users `ios` 

`AG007` app_group/get_managers_by_group_id


**ios此地方call了13次api**

####  新增拜訪_選擇聯絡人 個人客戶

`CT103` contacter/get_company_and_user_list

####  新增拜訪_選擇聯絡人 企業客戶
####  選擇公司

`CT103` contacter/get_company_and_user_list 客戶列表

`CT012` contacter/get_person_by_company_id android點擊後才call

####  選擇文件

`DF110` document/get_list_by_enterprise

###  點選文件

`SR032` schedule/upload_file_enterprise

###  新增拜訪完送出

`SR011` schedule/update_item

`SR056` schedule/set_record_id

`SR001` schedule/get_by_days 重新刷新拜訪頁 **ios會call好幾次api**

---

#  首頁_日報

###  日報列表

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%97%A5%E5%A0%B1%E5%88%97%E8%A1%A8.png" width = "300" height = "500" alt="日報列表" align=center />  

`AU087` app_user_daily/get_list 會call多次api

###  新增/編輯日報

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E5%A2%9E_%E7%B7%A8%E8%BC%AF%E6%97%A5%E5%A0%B1.png" width = "300" height = "500" alt="新增_編輯日報" align=center />  

`AU085` app_user_daily/update_item

---

#  首頁_群組

###  群組列表

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%BE%A4%E7%B5%84%E5%88%97%E8%A1%A8.png" width = "300" height = "500" alt="群組列表" align=center />  


`AG015` app_group/get_groups_by_enterprise

###  點擊群組

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%BB%9E%E6%93%8A%E7%BE%A4%E7%B5%84.png" width = "300" height = "500" alt="點擊群組" align=center />  

`AG007` app_group/get_managers_by_group_id 

`AG014` app_group/get_subgroups

`AG031` app_group/get_managers_by_user `ios`

`AG009` app_group/get_users_by_main_group

###  點擊成員

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%BB%9E%E6%93%8A%E6%88%90%E5%93%A1.png" width = "300" height = "500" alt="點擊成員" align=center />  

`AU052` app_user/get_user `ios`

### 新增成員

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E5%A2%9E%E6%88%90%E5%93%A1.png" width = "300" height = "500" alt="新增成員" align=center />  

`AG016` app_group/get_package_by_enterprise

###  新增成員_確認

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E5%A2%9E%E6%88%90%E5%93%A1_%E7%A2%BA%E8%AA%8D.png" width = "300" height = "500" alt="新增成員_確認" align=center />  

`AU044` app_user/get_users_by_cellphone_batch

`AU045` app_user/send_invite_sms

###  編輯成員

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%B7%A8%E8%BC%AF%E6%88%90%E5%93%A1.png" width = "300" height = "500" alt="編輯成員" align=center />  

`AU052` app_user/get_user `ios`

###  刪除成員

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E5%88%AA%E9%99%A4%E6%88%90%E5%93%A1.png" width = "300" height = "500" alt="刪除成員" align=center />  

`AG003` app_group/user_remove

###  新建子群組

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E5%BB%BA%E5%AD%90%E7%BE%A4%E7%B5%84.png" width = "300" height = "500" alt="新建子群組" align=center />  

`AG012` app_group/update_subgroup

`AG017` app_group/get_group_item `ios`

###  點擊子群組

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%BB%9E%E6%93%8A%E5%AD%90%E7%BE%A4%E7%B5%84.png" width = "300" height = "500" alt="點擊子群組" align=center />  

`G006` app_group/get_users

`G007` app_group/get_managers_by_group_id

---

#  首頁_消息

###  消息列表

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%B6%88%E6%81%AF%E5%88%97%E8%A1%A8.png" width = "300" height = "500" alt="消息列表" align=center />  

`U095` app_user_notify/get_list_by_user

###  點擊消息_拜訪

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E9%BB%9E%E6%93%8A%E6%B6%88%E6%81%AF.png" width = "300" height = "500" alt="點擊消息_拜訪" align=center />  

`U096` app_user_notify/get_item_by_id   怪 ios任務會call兩次

`AU093` app_user_notify/set_status_hide

以下詳細拜訪資訊
`SR002` schedule/get_item_by_id

`SR005` schedule/get_feedback_by_feedback_id


`CT013` contacter/get_company_by_id

`CT004` contacter/get_company_near_by_gps

以下為任務
`SR002` schedule/get_item_by_id


`U096` app_user_notify/get_item_by_id

`AU093` app_user_notify/set_status_hide

以下為公告
`AU093` app_user_notify/set_status_hide

`U096` app_user_notify/get_item_by_id

以下為考勤
`U096` app_user_notify/get_item_by_id

`AU093` app_user_notify/set_status_hide

---

#  日曆

###  日曆列表

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%97%A5%E6%9B%86%E5%88%97%E8%A1%A8.png" width = "300" height = "500" alt="日曆列表" align=center />  

`SR001` schedule/get_by_days ios會call多次

###  詳細內容
同拜訪或任務

事項
`SR002` schedule/get_item_by_id

###  新增行程

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%B0%E5%A2%9E%E8%A1%8C%E7%A8%8B.png" width = "300" height = "500" alt="新增行程" align=center />  


`SR011` schedule/update_item

---

#  聯繫

###  聯絡人列表


`CT103` contacter/get_company_and_user_list

###  搜尋聯絡人

`CT103` contacter/get_company_and_user_list
**ios搜尋時沒搜尋內容也會call**

`CT103` contacter/get_company_and_user_list `android`

###  聯絡人排序

`CT103` contacter/get_company_and_user_list

###  點擊聯絡人

`CT013` contacter/get_company_by_id

`CT012` contacter/get_person_by_company_id

###  聯絡人相關資訊

`CT015` contacter/get_research_by_id `ios`

### 聯絡人拜訪歷史紀錄

`CT016` contacter/get_schedules_by_company_id

###  編輯聯絡人

`CT021` contacter/update_company

`CT024` contacter/delete_person ios沒刪除聯絡人也會call

`CT023` contacter/update_person

`CT005` contacter/get_company_by_name_batch `android`

###  新增聯絡人(企業)

`CT005` contacter/get_company_by_name_batch

`CT021` contacter/update_company

`CT023` contacter/update_person

###  新增聯絡人(個人)

`CT023` contacter/update_person

---

#  考勤

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E8%80%83%E5%8B%A4.png" width = "300" height = "500" alt="考勤" align=center />  

`AU066` app_user_attendance/get_attendance_flow_by_manager

`AU067` app_user_attendance/get_log_by_month_with_user


`SC001` system_config/get_groups_by_user `android`

###  簽到

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%B0%BD%E5%88%B0.png" width = "300" height = "500" alt="簽到" align=center />  

###  簽退

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%B0%BD%E9%80%80.png" width = "300" height = "500" alt="簽退" align=center />  

`AU063` app_user_attendance/add_attendance `android`

`AU067` app_user_attendance/get_log_by_month_with_user

###  我的記錄

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%88%91%E7%9A%84%E7%B4%80%E9%8C%84.png" width = "300" height = "500" alt="我的記錄" align=center />  

`AU067` app_user_attendance/get_log_by_month_with_user ios會call三次

###  考勤詳細記錄

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E8%80%83%E5%8B%A4%E8%A9%B3%E7%B4%B0%E8%A8%98%E9%8C%84.png" width = "300" height = "500" alt="考勤詳細記錄" align=center />  

`AU062` app_user_attendance/get_attendance_by_day `android`

###  群組考勤

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%BE%A4%E7%B5%84%E8%80%83%E5%8B%A4.png" width = "300" height = "500" alt="群組考勤" align=center />  

`AU066` app_user_attendance/get_attendance_flow_by_manager


`AG009` app_group/get_users_by_main_group `android`  call多次api

`AG010` app_group/get_users_by_enterprise_group `android`

`AG007` app_group/get_managers_by_group_id `android`

###  選擇成員

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%BE%A4%E9%A7%94%E8%80%83%E5%8B%A4_%E9%81%B8%E6%93%87%E6%88%90%E5%93%A1.png" width = "300" height = "500" alt="群組考勤_選擇成員" align=center />  

`AU067` app_user_attendance/get_log_by_month_with_user

---

#  文件

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%96%87%E4%BB%B6.png" width = "300" height = "500" alt="文件" align=center />  

`DF110` document/get_list_by_enterprise

###  搜尋文件

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%90%9C%E5%B0%8B%E6%96%87%E4%BB%B6.png" width = "300" height = "500" alt="搜尋文件" align=center />  


`DF111` document/search_by_enterprise `android`

---

#  設定

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E8%A8%AD%E5%AE%9A.png" width = "300" height = "500" alt="設定" align=center />  

`AU051` app_user/get_groups `android`


`AG031` app_group/get_managers_by_user `android`

`AG032` app_group/get_allgroups_by_enterprise `android` 

`AG010` app_group/get_users_by_enterprise_group `android`

###  個人QR code

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E5%80%8B%E4%BA%BAQRcode.png" width = "300" height = "500" alt="個人QR code" align=center />  

`SC032` system_config/gen_qrcode

###  更改姓名

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E6%9B%B4%E6%94%B9%E5%A7%93%E5%90%8D.png" width = "300" height = "500" alt="更改姓名" align=center />  

`AU042` app_user/update_name

###  修改密碼

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E4%BF%AE%E6%94%B9%E5%AF%86%E7%A2%BC.png" width = "300" height = "500" alt="修改密碼" align=center />  

`AU041` app_user/update_secret

###  Q&A

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/Q%26A.png" width = "300" height = "500" alt="Q&A" align=center />  

`SC033` system_config/get_faq

###  聯絡skywind

<img src="https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E8%81%AF%E7%B5%A1skywind.png" width = "300" height = "500" alt="聯絡skywind" align=center />  

`SC035` system_config/get_config



  [1]: https://github.com/dogC76/wing_document/blob/master/%E5%9C%96/%E7%99%BB%E5%85%A5-01.png