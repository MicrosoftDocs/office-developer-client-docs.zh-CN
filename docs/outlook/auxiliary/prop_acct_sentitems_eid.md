---
title: PROP_ACCT_SENTITEMS_EID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: f199a97f-55d6-9297-adc4-e9f7b4b5f58b
description: 表示帐户已发送项目的默认文件夹的条目 ID。
ms.openlocfilehash: 24bb4714a4f4964ac3d84ea7a792e64da67599df
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431839"
---
# <a name="prop_acct_sentitems_eid"></a>PROP_ACCT_SENTITEMS_EID

表示帐户已发送项目的默认文件夹的条目 ID。 
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0020  <br/> |
|属性类型  <br/> |PT_BINARY  <br/> |
|属性标记：  <br/> |0x00200102  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>备注

使用 [IOlkAccount：：GetProp 获取此属性](iolkaccount-getprop.md)。
  
已发送项目的默认文件夹为 **"已发送项目"。**
  
此属性对于 POP3 和 IMAP 帐户为只读。 尝试为这些类型的帐户设置此属性将 **返回E_ACCT_NOT_FOUND。** 
  

