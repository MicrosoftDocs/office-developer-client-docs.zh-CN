---
title: IMAPISessionAdminServices
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISession.AdminServices
api_type:
- COM
ms.assetid: 487fab39-5c2c-4e1a-9f90-4da64f5e198b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c639523a02047bf00c378dafd7bc698d7d4e5fff
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405903"
---
# <a name="imapisessionadminservices"></a>IMAPISession::AdminServices

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回用于对邮件服务进行更改的[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。 
  
```cpp
HRESULT AdminServices(
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lppServiceAdmin_
  
> 排除指向邮件服务管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功返回了指向邮件服务管理对象的指针。
    
## <a name="notes-to-callers"></a>给调用方的说明

**IMAPISession:: AdminServices**方法创建一个邮件服务管理对象, 该对象是一个支持**IMsgServiceAdmin**接口的对象, 并返回一个指针。 通过使用此指针, 可以调用**IMsgServiceAdmin**方法来更改会话配置文件中的任何邮件服务。 请注意, 这些更改在下次会话之前不会生效;当前会话不受影响。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIStoreFunctions  <br/> |GetServerName  <br/> |MFCMAPI 使用**IMAPISession:: AdminServices**方法访问配置文件以读取服务器名称。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)
  
[IProfAdmin::AdminServices](iprofadmin-adminservices.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

