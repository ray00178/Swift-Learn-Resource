# Learing 關於自己工作開發上遇到困難的問題

## 1. 使用Fastlane包版時，因Fastfile指定的【provisioningProfiles】與本機不符且該憑證又過期，導致包版一直失敗

```text
error: exportArchive: No "iOS In House" profiles for team 'Sinyi Realty Estate Inc.' matching '003 Sinyi IM ShareExtension PROD_Dis' are installed.

error: exportArchive: Provisioning profile "003 Sinyi IM ShareExtension PROD_Dis" expired on Dec 23, 2021.

// 解決方式：更改為正確名稱及未過期即可
```

## 2. 包版時，專案的Build未填寫導致包版後無法安裝問題

![Learn-2 image](https://github.com/ray00178/Swift-Learn-Resource/blob/main/images/learn-2-1.png){:height="165px" width="600px"}

## 3. UICollectionViewFlowLayout，可以override targetContentOffset()，來自定滑動後的位置

![Learn-3 image](https://github.com/ray00178/Swift-Learn-Resource/blob/main/images/learn-3-1.png){:height="434px" width="600px"}
