---
title: PidTagPrimarySendAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e1bc4900-d261-f692-386b-139ef6960212
description: 指定邮件的主帐户发送时间戳。
ms.openlocfilehash: 902c71bd4a1bd5a25ab50c4b26bcfa6d5e8489e6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327704"
---
# <a name="pidtagprimarysendaccount"></a>PidTagPrimarySendAccount

指定邮件的主帐户"发送"标记。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PRIMARY_SEND_ACCOUNT  <br/> |
|标识符:  <br/> |0x0E28  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |帐户  <br/> |
   
## <a name="remarks"></a>备注

此属性适用于 MAPI 邮件对象。 对于收到的邮件，主帐户"发送"标记指示应发送转发或答复的帐户。 对于传出邮件，它将确定发送邮件使用哪个帐户。 其 [值为PROP_ACCT_SEND_STAMP发送](prop_acct_send_stamp.md) 邮件的帐户的 [IOlkAccount](iolkaccount.md) 接口中的值。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)
- [MAPI 属性](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx)
- [PidTagPrimarySendAccount 规范属性](https://msdn.microsoft.com/library/2f268b3b-2e4c-4aea-8879-bdd0ac1df35c%28Office.15%29.aspx)

