---
title: 为 MAPI 初始化 OLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 53b65299-69f8-4fc0-8d9b-f666e814aaac
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 87310916f4a54b308f0599ec5c1a4a3bfe83c376
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317225"
---
# <a name="initializing-ole-for-mapi"></a><span data-ttu-id="58c84-103">为 MAPI 初始化 OLE</span><span class="sxs-lookup"><span data-stu-id="58c84-103">Initializing OLE for MAPI</span></span>

  
  
<span data-ttu-id="58c84-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58c84-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58c84-105">如果还使用 OLE，请调用 OLE 函数 [OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) 以初始化 OLE 库。</span><span class="sxs-lookup"><span data-stu-id="58c84-105">If you also use OLE, call the OLE function [OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx) to initialize the OLE libraries.</span></span> <span data-ttu-id="58c84-106">**OleInitialize** 初始化会话的全局数据，并准备 OLE 库以接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="58c84-106">**OleInitialize** initializes global data for the session and prepares the OLE libraries to accept calls.</span></span> <span data-ttu-id="58c84-107">有关调用 **OleInitialize 的信息**，请参阅 Windows SDK。</span><span class="sxs-lookup"><span data-stu-id="58c84-107">For information about calling **OleInitialize**, see the Windows SDK.</span></span>
  

