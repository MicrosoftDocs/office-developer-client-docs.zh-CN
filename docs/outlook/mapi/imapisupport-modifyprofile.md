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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4c296b12d2dc98c4ff8d94349298e9dda0fb9409
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419987"
---
# <a name="imapisupportmodifyprofile"></a>IMAPISupport::ModifyProfile

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
永久更改邮件存储配置文件部分。
  
```cpp
HRESULT ModifyProfile(
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]指示邮件存储类型的标志位掩码。 可以设置以下标志：
    
MDB_TEMPORARY 
  
> 邮件存储是临时的，不应添加到邮件存储表中。 设置MDB_TEMPORARY时 **，ModifyProfile** 将立即S_OK返回。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对配置文件部分所做的更改已成功。
    
## <a name="remarks"></a>备注

**IMAPISupport：：ModifyProfile** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序调用 **ModifyProfile** 以提示 MAPI 修改其配置文件信息。 
  
 **ModifyProfile** 将与调用提供程序关联的配置文件节添加到已安装的邮件存储提供程序资源列表中。 这将导致消息存储表中列出的消息存储，该表通过 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 方法对客户端可用，并且打开时不显示对话框。 
  
如果设置了 MDB_TEMPORARY 标志，MAPI 不执行任何操作，并且该方法将立即返回 S_OK。
  
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

