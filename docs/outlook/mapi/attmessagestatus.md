---
title: attMessageStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8f55470a-65b3-4210-a7d2-9031cb17ca80
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 704707b34fb4532f0e60636df31edbae1a939f35
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565744"
---
# <a name="attmessagestatus"></a>attMessageStatus

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 邮件标志映射到 TNEF 标志保留向后兼容性。 所有标志的组合在一起，并单字节编码。 映射如下所示：
  
|**MAPI 邮件标志**|**TNEF 标志**|
|:-----|:-----|
|MSGFLAG_READ  <br/> |fmsRead  <br/> |
|MSGFLAG_UNMODIFED  <br/> |~ fmsModified  <br/> |
|MSGFLAG_SUBMIT  <br/> |fmsSubmitted  <br/> |
|MSGFLAG_HASATTACH  <br/> |fmsHasAttach  <br/> |
|MSGFLAG_UNSENT  <br/> |fmsLocal  <br/> |
   
这些标志 TNEF 中定义。H 头文件。
  

