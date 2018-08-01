---
title: PROP_ACCT_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b72124aa-2e85-057c-9343-a40af60b91a0
description: 返回一个唯一标识在其中创建该帐户的配置文件中的帐户的标识符。
ms.openlocfilehash: a4ae193b89132ea718e16aec82f592205f9771c3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774435"
---
# <a name="propacctid"></a>PROP_ACCT_ID

返回一个唯一标识在其中创建该帐户的配置文件中的帐户的标识符。
  
## <a name="quick-info"></a>快速信息

See [IOlkAccount](iolkaccount.md).
  
|||
|:-----|:-----|
|标识符:  <br/> |0x0001  <br/> |
|属性类型  <br/> |PT_LONG  <br/> |
|属性标记：  <br/> |0x00010003  <br/> |
|访问权限  <br/> |只读  <br/> |
   
## <a name="remarks"></a>说明

通过使用[IOlkAccount::GetProp](iolkaccount-getprop.md)获取此属性。 如果客户端试图设置该属性，则此属性返回**E_OLK_PROP_READ_ONLY**。 
  
此属性是不同[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md) ，其值是仅唯一在其中创建该帐户，该配置文件中的所有帐户，而**属性\_ACCT_MINI_UID**唯一标识中的帐户和以外的在其中创建该帐户的配置文件。 当包含这些属性的消息漫游到其他 Outlook 配置文件的第二个计算机和组不同的帐户， **PROP_ACCT_ID**可以可能发生冲突的第二台计算机和**PROP_ACCT_MINI_UID**的配置文件中的帐户可以唯一标识原始的配置文件中的原始帐户。 
  
## <a name="see-also"></a>另请参阅

- [有关帐户管理 API](about-the-account-management-api.md)  
- [常量 （帐户管理 API）](constants-account-management-api.md)

