---
title: MAPIAdminProfiles
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIAdminProfiles
api_type:
- HeaderDef
ms.assetid: 82a9e379-39e4-4257-8cba-a6758f431cdc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5043a614ccd94994fe86838f15aa1a43f22733e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412350"
---
# <a name="mapiadminprofiles"></a>MAPIAdminProfiles

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建配置文件管理对象。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT MAPIAdminProfiles(
  ULONG ulFlags,
  LPPROFADMIN FAR * lppProfAdmin
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时指示服务输入函数选项的标志的位掩码。 
    
 _lppProfAdmin_
  
> 排除指向新的配置文件管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIObjects  <br/> |CMapiObjects:: GetProfAdmin  <br/> |MFCMAPI 使用**MAPIAdminProfiles**方法获取配置文件管理对象。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IProfAdmin::CreateProfile](iprofadmin-createprofile.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

