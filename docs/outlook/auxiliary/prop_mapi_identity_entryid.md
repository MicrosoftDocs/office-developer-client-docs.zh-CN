---
title: PROP_MAPI_IDENTITY_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c64db8ea-d6ad-4fb9-97aa-958e5a0daf8f
description: 检索或设置帐户的通讯簿条目 ID。
ms.openlocfilehash: 2352f64b46e9884e95b7bf1f3693321f7cd224ca
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326430"
---
# <a name="prop_mapi_identity_entryid"></a>PROP_MAPI_IDENTITY_ENTRYID

检索或设置帐户的通讯簿条目 ID。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x2002  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x20020102  <br/> |
|访问权限  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

 **PROP \_MAPI \_ IDENTITY \_ ENTRYID** 不应存在于每个帐户上。 例如，Exchange 帐户可以设置 **PROP \_ MAPI \_ IDENTITY \_ ENTRYID，** 而不是 [PROP \_ ACCT_USER_EMAIL_ADDR](prop_acct_user_email_addr.md)，而对于 SMTP/POP3 帐户，情况将反转。 **PROP \_MAPI_IDENTITY_ENTRYID** 返回条目 ID，该值类似于 [IMAPISession：：QueryIdentity](https://msdn.microsoft.com/library/a2cdda90-5457-49a7-b98c-7273ffe5cbbc%28Office.15%29.aspx)中的 _lppEntryID_ 返回的值。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)

