---
title: PidTagPrimarySendAccount
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: e1bc4900-d261-f692-386b-139ef6960212
description: 指定邮件主 accountsendstamp。
ms.openlocfilehash: 902c71bd4a1bd5a25ab50c4b26bcfa6d5e8489e6
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25394081"
---
# <a name="pidtagprimarysendaccount"></a>PidTagPrimarySendAccount

指定一条消息的主帐户"发送"戳。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |PR_PRIMARY_SEND_ACCOUNT  <br/> |
|标识符：  <br/> |0x0E28  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Account  <br/> |
   
## <a name="remarks"></a>说明

此属性适用于 MAPI message 对象。 收到的邮件，主帐户"发送"戳指示转发或答复应发送使用的帐户。 对于传出消息，它确定要发送邮件的帐户。 其值是帐户的用于发送邮件的[IOlkAccount](iolkaccount.md)接口的[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md)值。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)
- [MAPI 属性](https://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx)
- [PidTagPrimarySendAccount 规范属性](https://msdn.microsoft.com/library/2f268b3b-2e4c-4aea-8879-bdd0ac1df35c%28Office.15%29.aspx)

