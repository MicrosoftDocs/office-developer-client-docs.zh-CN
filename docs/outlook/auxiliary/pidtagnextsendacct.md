---
title: PidTagNextSendAcct
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1cf5b314-39fa-996f-fd88-00380ffbc4de
description: 指定邮件的辅助 accountsendstamp。
ms.openlocfilehash: 3aa88a1fd5a73cc4ae2e990e6dad0697083bb694
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327711"
---
# <a name="pidtagnextsendacct"></a>PidTagNextSendAcct

指定邮件的辅助帐户"发送"标记。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |PR_NEXT_SEND_ACCT  <br/> |
|标识符:  <br/> |0x0E29  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Outlook应用程序  <br/> |
   
## <a name="remarks"></a>备注

此属性适用于 MAPI 邮件对象。 对于收到的邮件，如果转发或答复不能使用主帐户发送，则辅助帐户"发送"标记指示应发送转发或答复的帐户。 对于传出邮件，如果无法使用主帐户发送邮件，则辅助帐户"发送"标记将确定发送邮件的帐户。 其 [值为PROP_ACCT_SEND_STAMP发送](prop_acct_send_stamp.md) 邮件的帐户的 [IOlkAccount](iolkaccount.md) 接口中的值。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)
- [MAPI 属性](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx) 
- [PidTagNextSendAcct 规范属性](https://msdn.microsoft.com/library/b7429c2e-0d9d-4921-9f56-9ecad817f8cb%28Office.15%29.aspx)

