---
title: 避免使用 IStreamSetSize 扩展流
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b6de594f-e331-4421-956b-86ee0b5518fe
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 614bb3d142b7aaabe89223b6ce3552469edfce27
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428912"
---
# <a name="avoiding-using-istreamsetsize-to-extend-a-stream"></a>避免使用 IStream：：SetSize 扩展流

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在写入流时，有时必须放大它们，因为它们的初始大小不再足够。 使用 OLE 方法 **IStream：：Write** 完成此操作，而不是 **IStream：：SetSize**。 **IStream：：Write** 自动扩展流，使 ** IStream：：SetSize ** 不必要。 在没有 IStream：：SetSize 的情况下调用 **IStream：：Write** 的速度最多比在 Write 之前进行 **SetSize** 调用快 **三倍**。 
  

