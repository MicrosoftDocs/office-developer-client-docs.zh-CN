---
title: 使用 IStreamDocfile 打开 OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f91df63c-ff6d-4c63-a665-5bcfdabe7e0e
description: '上次修改时间: 2006 年7月2012'
ms.openlocfilehash: 2de13be34e8d81f88bfba872dda6e5534eb431bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326227"
---
# <a name="opening-ole-attachments-with-istreamdocfile"></a><span data-ttu-id="4a436-103">使用 IStreamDocfile 打开 OLE 附件</span><span class="sxs-lookup"><span data-stu-id="4a436-103">Opening OLE attachments with IStreamDocfile</span></span>

<span data-ttu-id="4a436-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a436-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a436-105">打开 OLE 对象附件时, 请使用**IStreamDocfile**接口, 而不是[IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034%28v=vs.85%29.aspx)或[IStorage](https://msdn.microsoft.com/library/windows/desktop/aa380015%28v=vs.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a436-105">When opening an OLE object attachment, use the **IStreamDocfile** interface rather than [IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034%28v=vs.85%29.aspx) or [IStorage](https://msdn.microsoft.com/library/windows/desktop/aa380015%28v=vs.85%29.aspx).</span></span> 

<span data-ttu-id="4a436-106">**IStreamDocfile**提供了使用结构化存储的直接访问对象, 消除了执行复制操作和减少开销的需求。</span><span class="sxs-lookup"><span data-stu-id="4a436-106">**IStreamDocfile** provides direct access to the object using structured storage, eliminating the need to perform a copy operation and reducing overhead.</span></span> <span data-ttu-id="4a436-107">**IStreamDocfile**是一个特定的**IStream**实现, 可保证流的内容被格式化为结构化存储。</span><span class="sxs-lookup"><span data-stu-id="4a436-107">**IStreamDocfile** is a specific implementation of **IStream** with the content of the stream guaranteed to be formatted as structured storage.</span></span> <span data-ttu-id="4a436-108">**IStreamDocfile**是由邮件存储提供程序实现的。</span><span class="sxs-lookup"><span data-stu-id="4a436-108">**IStreamDocfile** is implemented by message store providers.</span></span> 
  

