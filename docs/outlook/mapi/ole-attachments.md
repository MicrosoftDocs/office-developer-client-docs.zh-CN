---
title: OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: febb6a5e-7c40-4f21-806e-7f827d1c37cf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ccd4a77e74a4a4cbdfcd8474d4cc00d0d0516839
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584637"
---
# <a name="ole-attachments"></a><span data-ttu-id="940ec-103">OLE 附件</span><span class="sxs-lookup"><span data-stu-id="940ec-103">OLE Attachments</span></span>

  
  
<span data-ttu-id="940ec-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="940ec-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="940ec-105">附件的 OLE 对象被编码为向后兼容性的 OLE 1 stream 对象。</span><span class="sxs-lookup"><span data-stu-id="940ec-105">Attachments that are OLE objects are encoded as OLE 1 stream objects for backward compatibility.</span></span> <span data-ttu-id="940ec-106">如果原始对象确实是 OLE 2 **IStorage**对象，该对象必须要转换到 OLE 1 流。</span><span class="sxs-lookup"><span data-stu-id="940ec-106">If the original object is really an OLE 2 **IStorage** object, then the object must be converted to an OLE 1 stream.</span></span> <span data-ttu-id="940ec-107">使用**OleConvertIStorageToOLESTREAM**函数，它是 Win32 OLE 库的一部分，则执行此转换。</span><span class="sxs-lookup"><span data-stu-id="940ec-107">This conversion is performed using the **OleConvertIStorageToOLESTREAM** function, which is part of the Win32 OLE libraries.</span></span> 
  

