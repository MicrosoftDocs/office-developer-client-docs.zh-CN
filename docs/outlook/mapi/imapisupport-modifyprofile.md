---
title: IMAPISupportModifyProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.ModifyProfile
api_type:
- COM
ms.assetid: 33bef4ea-d6c0-4455-b95d-4b29edb9c0bc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b16730681b5414f28ae45be7195b4fa551bf0e82
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591987"
---
# <a name="imapisupportmodifyprofile"></a>IMAPISupport::ModifyProfile

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
对做的更改一条消息存储永久的配置文件部分。
  
```cpp
HRESULT ModifyProfile(
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]存储一个位掩码的标志，指示邮件的类型。 可以设置以下标记：
    
MDB_TEMPORARY 
  
> 消息存储库是临时，不应添加到消息存储表。 当设置 MDB_TEMPORARY 时， **ModifyProfile**立即返回 S_OK。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对配置文件部分的更改都是成功的。
    
## <a name="remarks"></a>注解

消息存储提供程序支持对象的实现**IMAPISupport::ModifyProfile**方法。 消息存储提供程序调用**ModifyProfile**提示 MAPI 修改其配置文件信息。 
  
 **ModifyProfile**添加到已安装的消息存储提供程序资源的列表的呼叫提供程序相关联的配置文件部分。 此时会列出在消息存储表中，可供客户端通过[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法，并打开，也不显示的对话框中的消息存储。 
  
如果设置了 MDB_TEMPORARY 标志，MAPI 不执行任何操作并与 S_OK 立即返回的方法。
  
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

