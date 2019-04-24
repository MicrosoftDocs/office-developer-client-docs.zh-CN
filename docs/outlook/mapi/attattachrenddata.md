---
title: attAttachRenddata
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c510b7a5-0f55-46af-bddb-40a8195a84d4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d58fc0eae5401773d28f5bbe510913ff381ade8d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331911"
---
# <a name="attattachrenddata"></a>attAttachRenddata

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**attAttachRenddata**属性被编码为**RENDDATA**结构, 该结构描述了邮件文本中的附件呈现方式和位置。 **RENDDATA**结构简单地在 TNEF 流中编码为从**RENDDATA**结构的第一个成员开始的**sizeof (RENDDATA)** 字节。 如果**RENDDATA**结构的**dwFlags**成员的值设置为**MAC_BINARY**, 则以下附件的数据将存储为 MacBinary 格式;否则, 附件数据将按通常方式进行编码。
  

