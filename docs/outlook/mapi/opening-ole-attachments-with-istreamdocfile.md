---
title: 与 IStreamDocfile 打开 OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f91df63c-ff6d-4c63-a665-5bcfdabe7e0e
description: 上次修改时间： 2012 年 7 月 6 日
ms.openlocfilehash: 2de13be34e8d81f88bfba872dda6e5534eb431bd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386549"
---
# <a name="opening-ole-attachments-with-istreamdocfile"></a><span data-ttu-id="3de43-103">与 IStreamDocfile 打开 OLE 附件</span><span class="sxs-lookup"><span data-stu-id="3de43-103">Opening OLE attachments with IStreamDocfile</span></span>

<span data-ttu-id="3de43-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3de43-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3de43-105">在打开附件 OLE 对象时，使用**IStreamDocfile**接口而不是[IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034%28v=vs.85%29.aspx)或[IStorage](https://msdn.microsoft.com/library/windows/desktop/aa380015%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3de43-105">When opening an OLE object attachment, use the **IStreamDocfile** interface rather than [IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034%28v=vs.85%29.aspx) or [IStorage](https://msdn.microsoft.com/library/windows/desktop/aa380015%28v=vs.85%29.aspx).</span></span> 

<span data-ttu-id="3de43-106">**IStreamDocfile**提供直接访问使用结构化的存储文件，不需要执行复制操作和减少开销的对象。</span><span class="sxs-lookup"><span data-stu-id="3de43-106">**IStreamDocfile** provides direct access to the object using structured storage, eliminating the need to perform a copy operation and reducing overhead.</span></span> <span data-ttu-id="3de43-107">**IStreamDocfile** **IStream**保证格式化为结构化存储 stream 的内容具体的实现。</span><span class="sxs-lookup"><span data-stu-id="3de43-107">**IStreamDocfile** is a specific implementation of **IStream** with the content of the stream guaranteed to be formatted as structured storage.</span></span> <span data-ttu-id="3de43-108">由消息存储提供程序实现**IStreamDocfile** 。</span><span class="sxs-lookup"><span data-stu-id="3de43-108">**IStreamDocfile** is implemented by message store providers.</span></span> 
  

