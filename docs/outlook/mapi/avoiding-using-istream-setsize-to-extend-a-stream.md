---
title: 避免使用 IStreamSetSize 扩展流
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b6de594f-e331-4421-956b-86ee0b5518fe
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 54d352c263fd34bc8494d8d76c76cb22e0bafa58
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774618"
---
# <a name="avoiding-using-istreamsetsize-to-extend-a-stream"></a>避免使用 IStream::SetSize 来扩展流

  
  
**适用于**： Outlook 
  
写入流，时，有时不必放大它们，因为其初始大小不再足够。 使用**IStream::Write**的 OLE 方法实现这一点而不是**IStream::SetSize**。 **IStream::Write**自动扩展流，使 * * IStream::SetSize * * 不必要。 调用不带**IStream::SetSize** **IStream::Write**可以比进行**写入**之前调用**SetSize**速度更快是三倍。
  

