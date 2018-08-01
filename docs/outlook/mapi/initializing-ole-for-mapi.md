---
title: 初始化 MAPI 的 OLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 53b65299-69f8-4fc0-8d9b-f666e814aaac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6efe41c79cd85eb844ee19b8c54e200956c9b2a3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775926"
---
# <a name="initializing-ole-for-mapi"></a><span data-ttu-id="668d9-103">初始化 MAPI 的 OLE</span><span class="sxs-lookup"><span data-stu-id="668d9-103">Initializing OLE for MAPI</span></span>

  
  
<span data-ttu-id="668d9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="668d9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="668d9-105">如果您还使用 OLE，调用 OLE 函数[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx)初始化 OLE 库。</span><span class="sxs-lookup"><span data-stu-id="668d9-105">If you also use OLE, call the OLE function [OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx) to initialize the OLE libraries.</span></span> <span data-ttu-id="668d9-106">**OleInitialize**会话初始化全局数据，并准备 OLE 库以接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="668d9-106">**OleInitialize** initializes global data for the session and prepares the OLE libraries to accept calls.</span></span> <span data-ttu-id="668d9-107">调用**OleInitialize**有关的信息，请参阅 Windows SDK。</span><span class="sxs-lookup"><span data-stu-id="668d9-107">For information about calling **OleInitialize**, see the Windows SDK.</span></span>
  

