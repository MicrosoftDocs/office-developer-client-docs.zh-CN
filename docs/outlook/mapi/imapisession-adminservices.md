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
ms.openlocfilehash: cb7fa7bb7dc17a89fc7cc40ae370accc40fa3941
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579836"
---
# <a name="imapisessionadminservices"></a>IMAPISession::AdminServices

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回对消息服务的更改[IMsgServiceAdmin](imsgserviceadminiunknown.md)指针。 
  
```cpp
HRESULT AdminServices(
  ULONG ulFlags,
  LPSERVICEADMIN FAR * lppServiceAdmin
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lppServiceAdmin_
  
> [输出]指向与邮件服务管理对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回指向消息服务管理对象的指针。
    
## <a name="notes-to-callers"></a>给调用方的说明

**IMAPISession::AdminServices**方法创建一个邮件服务管理对象，一个对象，支持**IMsgServiceAdmin**接口并返回一个指针。 通过使用此指针，您可以调用**IMsgServiceAdmin**方法来更改任何会话配置文件中的邮件服务。 请注意，这些更改才会生效直到下一个会话;当前会话会受到影响。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIStoreFunctions.cpp  <br/> |GetServerName  <br/> |MFCMAPI 使用**IMAPISession::AdminServices**方法来访问的配置文件读取的服务器名称。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgServiceAdmin : IUnknown](imsgserviceadminiunknown.md)
  
[IProfAdmin::AdminServices](iprofadmin-adminservices.md)
  
[IMAPISession : IUnknown](imapisessioniunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

