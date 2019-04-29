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
  
对邮件存储库配置文件部分进行永久性更改。
  
```cpp
HRESULT ModifyProfile(
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时指示邮件存储类型的标志的位掩码。 可以设置以下标志:
    
MDB_TEMPORARY 
  
> 邮件存储区是临时的, 不应添加到邮件存储库表中。 如果设置了 MDB_TEMPORARY, 则**ModifyProfile**将立即返回 S_OK。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 对配置文件部分所做的更改已成功。
    
## <a name="remarks"></a>说明

为邮件存储提供程序支持对象实现了**IMAPISupport:: ModifyProfile**方法。 邮件存储提供程序调用**ModifyProfile**以提示 MAPI 修改其配置文件信息。 
  
 **ModifyProfile**将与调用提供程序关联的配置文件节添加到已安装的邮件存储提供程序资源列表中。 这会使邮件存储在邮件存储表中列出, 该表可通过[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)方法供客户端使用, 并在不显示对话框的情况下打开。 
  
如果设置了 MDB_TEMPORARY 标志, MAPI 将不执行任何操作, 并且方法将立即返回 S_OK。
  
## <a name="see-also"></a>另请参阅



[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

