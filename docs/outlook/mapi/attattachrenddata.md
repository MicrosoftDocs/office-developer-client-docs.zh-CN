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
ms.openlocfilehash: d8c6699ac1bc5687b1c885d156535e5b54b93140
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774576"
---
# <a name="attattachrenddata"></a>attAttachRenddata

  
  
**适用于**： Outlook 
  
**AttAttachRenddata**属性被编码为**RENDDATA**结构，描述如何和附件呈现消息文本中的位置。 **RENDDATA**结构是只需编码 TNEF 用于将 stream 中为**sizeof(RENDDATA)** 字节开头**RENDDATA**结构中的第一个成员。 如果**RENDDATA**结构的**dwFlags**成员的值设置为**MAC_BINARY**，以下附件的数据存储在 MacBinary 格式;否则，像往常一样编码附件数据。
  

