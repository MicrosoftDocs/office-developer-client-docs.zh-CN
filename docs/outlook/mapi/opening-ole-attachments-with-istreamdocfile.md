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
ms.openlocfilehash: 1e11d9f663384f00e7fd867802ef63afe1dd7e9e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592736"
---
# <a name="opening-ole-attachments-with-istreamdocfile"></a><span data-ttu-id="41fb8-103">与 IStreamDocfile 打开 OLE 附件</span><span class="sxs-lookup"><span data-stu-id="41fb8-103">Opening OLE attachments with IStreamDocfile</span></span>

<span data-ttu-id="41fb8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="41fb8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="41fb8-105">在打开附件 OLE 对象时，使用**IStreamDocfile**接口而不是[IStream](http://msdn.microsoft.com/en-us/library/windows/desktop/aa380034%28v=vs.85%29.aspx)或[IStorage](http://msdn.microsoft.com/en-us/library/windows/desktop/aa380015%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41fb8-105">When opening an OLE object attachment, use the **IStreamDocfile** interface rather than [IStream](http://msdn.microsoft.com/en-us/library/windows/desktop/aa380034%28v=vs.85%29.aspx) or [IStorage](http://msdn.microsoft.com/en-us/library/windows/desktop/aa380015%28v=vs.85%29.aspx).</span></span> 

<span data-ttu-id="41fb8-106">**IStreamDocfile**提供直接访问使用结构化的存储文件，不需要执行复制操作和减少开销的对象。</span><span class="sxs-lookup"><span data-stu-id="41fb8-106">**IStreamDocfile** provides direct access to the object using structured storage, eliminating the need to perform a copy operation and reducing overhead.</span></span> <span data-ttu-id="41fb8-107">**IStreamDocfile** **IStream**保证格式化为结构化存储 stream 的内容具体的实现。</span><span class="sxs-lookup"><span data-stu-id="41fb8-107">**IStreamDocfile** is a specific implementation of **IStream** with the content of the stream guaranteed to be formatted as structured storage.</span></span> <span data-ttu-id="41fb8-108">由消息存储提供程序实现**IStreamDocfile** 。</span><span class="sxs-lookup"><span data-stu-id="41fb8-108">**IStreamDocfile** is implemented by message store providers.</span></span> 
  

