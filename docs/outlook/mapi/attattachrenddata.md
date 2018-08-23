---
title: attAttachRenddata
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c510b7a5-0f55-46af-bddb-40a8195a84d4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a006c126ec5e0fb86847226195efd03f7ae5351f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569447"
---
# <a name="attattachrenddata"></a>attAttachRenddata

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
**AttAttachRenddata**属性被编码为**RENDDATA**结构，描述如何和附件呈现消息文本中的位置。 **RENDDATA**结构是只需编码 TNEF 用于将 stream 中为**sizeof(RENDDATA)** 字节开头**RENDDATA**结构中的第一个成员。 如果**RENDDATA**结构的**dwFlags**成员的值设置为**MAC_BINARY**，以下附件的数据存储在 MacBinary 格式;否则，像往常一样编码附件数据。
  

