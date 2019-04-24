---
title: PROP_ACCT_SENTITEMS_EID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f199a97f-55d6-9297-adc4-e9f7b4b5f58b
description: 代表帐户的已发送项目的默认文件夹的条目 ID。
ms.openlocfilehash: 24bb4714a4f4964ac3d84ea7a792e64da67599df
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327585"
---
# <a name="propacctsentitemseid"></a>PROP_ACCT_SENTITEMS_EID

代表帐户的已发送项目的默认文件夹的条目 ID。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0020  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x00200102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>注解

使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)获取此属性。
  
"已发送邮件" 的默认文件夹为 "已**发送**邮件"。
  
对于 POP3 和 IMAP 帐户, 此属性是只读的。 尝试为这些类型的帐户设置此属性将返回**E_ACCT_NOT_FOUND**。 
  

