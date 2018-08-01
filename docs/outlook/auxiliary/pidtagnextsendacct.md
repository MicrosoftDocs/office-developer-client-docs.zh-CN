---
title: PidTagNextSendAcct
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 1cf5b314-39fa-996f-fd88-00380ffbc4de
description: 指定辅助 accountsendstamp 的邮件。
ms.openlocfilehash: 63d98382ff8a5a545cdb015c089c7b0a38926138
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774429"
---
# <a name="pidtagnextsendacct"></a>PidTagNextSendAcct

指定的第二帐户"发送"戳的邮件。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|相关属性：  <br/> |PR_NEXT_SEND_ACCT  <br/> |
|标识符：  <br/> |0x0E29  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |Outlook 应用程序  <br/> |
   
## <a name="remarks"></a>说明

此属性适用于 MAPI message 对象。 收到的邮件，辅助帐户"发送"戳指示转发或答复应发送，使用的帐户，如果不能转发或答复发送与主帐户。 对于传出消息，辅助帐户"发送"戳确定使用哪些帐户发送邮件，如果无法与主帐户发送邮件。 其值是帐户的用于发送邮件的[IOlkAccount](iolkaccount.md)接口的[PROP_ACCT_SEND_STAMP](prop_acct_send_stamp.md)值。 
  
## <a name="see-also"></a>另请参阅

- [常量 （帐户管理 API）](constants-account-management-api.md)
- [MAPI 属性](http://msdn.microsoft.com/library/3b980217-b65b-442b-8c18-b8b9f3ff487a%28Office.15%29.aspx) 
- [PidTagNextSendAcct 规范属性](http://msdn.microsoft.com/library/b7429c2e-0d9d-4921-9f56-9ecad817f8cb%28Office.15%29.aspx)

