---
title: PROP_ACCT_SENTITEMS_EID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f199a97f-55d6-9297-adc4-e9f7b4b5f58b
description: 表示的帐户已发送邮件的默认文件夹的条目 ID。
ms.openlocfilehash: 7795e8a112f0575b764fd55e92d27c7085e3d3a0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774428"
---
# <a name="propacctsentitemseid"></a>PROP_ACCT_SENTITEMS_EID

表示的帐户已发送邮件的默认文件夹的条目 ID。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0020  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x00200102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。
  
已发送邮件的默认文件夹是**已发送邮件**。
  
此属性是只读的 POP3 和 IMAP 帐户。 试图对这些类型的帐户设置此属性返回**E_ACCT_NOT_FOUND**。 
  

