---
title: 保存频繁使用的属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a8d4d575-7aa0-4542-91e2-322a6e400551
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e32ed3388e95d32a4857a933fb735d170dd71688
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424551"
---
# <a name="saving-frequently-used-properties"></a><span data-ttu-id="282a2-103">保存频繁使用的属性</span><span class="sxs-lookup"><span data-stu-id="282a2-103">Saving Frequently Used Properties</span></span>

  
  
<span data-ttu-id="282a2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="282a2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="282a2-105">通过存储需要时间和资源来检索并经常访问的数据来提高性能。</span><span class="sxs-lookup"><span data-stu-id="282a2-105">Improve performance by storing data that takes time and resources to retrieve and is accessed frequently.</span></span> <span data-ttu-id="282a2-106">有时, 使用额外的内存有时是一个更好的方法, 可重复检索。</span><span class="sxs-lookup"><span data-stu-id="282a2-106">Using extra memory can sometimes be a better option that repeated retrievals.</span></span> <span data-ttu-id="282a2-107">创建缓存以存储此数据时, 请务必谨慎。</span><span class="sxs-lookup"><span data-stu-id="282a2-107">Use caution and care when creating a cache for storing this data.</span></span> <span data-ttu-id="282a2-108">请注意, 设计低劣的缓存可能会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="282a2-108">Keep in mind that a poorly designed cache can negatively impact performance.</span></span>
  
<span data-ttu-id="282a2-109">例如, 大多数人际邮件 (IPM) 客户端需要在典型会话期间多次显示和打开文件夹的 IPM 子树。</span><span class="sxs-lookup"><span data-stu-id="282a2-109">For example, most interpersonal message (IPM) clients need to display and open the IPM subtree of folders many times during a typical session.</span></span> <span data-ttu-id="282a2-110">您可以通过存储每个文件夹的条目标识符来提高性能。</span><span class="sxs-lookup"><span data-stu-id="282a2-110">You can improve performance by storing the entry identifiers for each of these folders.</span></span> 
  

