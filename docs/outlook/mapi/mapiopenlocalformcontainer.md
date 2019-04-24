---
title: MAPIOpenLocalFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIOpenLocalFormContainer
api_type:
- COM
ms.assetid: 1c53170f-03a6-4a05-913e-de8eeadea692
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ace31079c51aac169f6091af0cb363e7f05f0d14
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270145"
---
# <a name="mapiopenlocalformcontainer"></a>MAPIOpenLocalFormContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回一个指向本地表单库的接口指针。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
MAPIOpenLocalFormContainer(
  LPMAPIFORMCONTAINER FAR * ppfcnt
);
```

## <a name="parameters"></a>参数

 _ppfcnt_
  
> 排除指向指向本地表单库接口的指针的指针。
    
## <a name="return-value"></a>返回值

无。
  
## <a name="remarks"></a>注解

第三方安装程序可使用指针返回到的接口, 将特定于应用程序的表单安装到库中, 而该程序首先不需要登录 MAPI。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg  <br/> |CMainDlg:: OnMAPIOpenLocalFormContainer  <br/> |MFCMAPI 使用**MAPIOpenLocalFormContainer**方法打开要在新窗口中呈现的本地表单容器。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

