---
title: 有关 outlook 导出的 Api
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 7b251308-70ff-a1ec-e968-9d5993909505
description: Outlook 将导出下列定义、 数据结构、 函数和接口原本供内部使用，但现已公开面向大众的文章。
ms.openlocfilehash: 0ed68b6c1b8082ee5cc22deb96333a0bd4d29390
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399366"
---
# <a name="about-apis-exported-by-outlook"></a><span data-ttu-id="7b2ec-103">有关 outlook 导出的 Api</span><span class="sxs-lookup"><span data-stu-id="7b2ec-103">About APIs exported by Outlook</span></span>

<span data-ttu-id="7b2ec-104">Outlook 将导出下列定义、 数据结构、 函数和接口原本供内部使用，但现已公开面向大众的文章。</span><span class="sxs-lookup"><span data-stu-id="7b2ec-104">Outlook exports the following definitions, data structures, functions, and interfaces that were originally designed for internal use but are now exposed for public consumption.</span></span>
  
### <a name="definitions"></a><span data-ttu-id="7b2ec-105">定义</span><span class="sxs-lookup"><span data-stu-id="7b2ec-105">Definitions</span></span>
  
- [<span data-ttu-id="7b2ec-106">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="7b2ec-106">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
    
### <a name="data-structures"></a><span data-ttu-id="7b2ec-107">数据结构</span><span class="sxs-lookup"><span data-stu-id="7b2ec-107">Data structures</span></span>
  
- [<span data-ttu-id="7b2ec-108">TZDEFINITION</span><span class="sxs-lookup"><span data-stu-id="7b2ec-108">TZDEFINITION</span></span>](tzdefinition.md)
    
- [<span data-ttu-id="7b2ec-109">TZREG</span><span class="sxs-lookup"><span data-stu-id="7b2ec-109">TZREG</span></span>](tzreg.md)
    
- [<span data-ttu-id="7b2ec-110">TZRULE</span><span class="sxs-lookup"><span data-stu-id="7b2ec-110">TZRULE</span></span>](tzrule.md)
    
### <a name="functions"></a><span data-ttu-id="7b2ec-111">函数</span><span class="sxs-lookup"><span data-stu-id="7b2ec-111">Functions</span></span>
  
- [<span data-ttu-id="7b2ec-112">HrCreateApptRebaser</span><span class="sxs-lookup"><span data-stu-id="7b2ec-112">HrCreateApptRebaser</span></span>](hrcreateapptrebaser.md)
    
- [<span data-ttu-id="7b2ec-113">HrProcessConvActionForSentItem</span><span class="sxs-lookup"><span data-stu-id="7b2ec-113">HrProcessConvActionForSentItem</span></span>](hrprocessconvactionforsentitem.md)
    
- [<span data-ttu-id="7b2ec-114">RebaseTaskComplete</span><span class="sxs-lookup"><span data-stu-id="7b2ec-114">RebaseTaskComplete</span></span>](rebasetaskcomplete.md)
    
- [<span data-ttu-id="7b2ec-115">RebaseTaskProgress</span><span class="sxs-lookup"><span data-stu-id="7b2ec-115">RebaseTaskProgress</span></span>](rebasetaskprogress.md)
    
### <a name="interfaces"></a><span data-ttu-id="7b2ec-116">接口</span><span class="sxs-lookup"><span data-stu-id="7b2ec-116">Interfaces</span></span>
  
- [<span data-ttu-id="7b2ec-117">IOlkApptRebaser</span><span class="sxs-lookup"><span data-stu-id="7b2ec-117">IOlkApptRebaser</span></span>](iolkapptrebaser.md)
    
### <a name="events"></a><span data-ttu-id="7b2ec-118">事件</span><span class="sxs-lookup"><span data-stu-id="7b2ec-118">Events</span></span>
  
- [<span data-ttu-id="7b2ec-119">可用的事件和其 dispid （Outlook 导出的 Api）</span><span class="sxs-lookup"><span data-stu-id="7b2ec-119">Available events and their dispids (Outlook exported APIs)</span></span>](available-events-and-their-dispids-outlook-exported-apis.md)
    
<span data-ttu-id="7b2ec-120">此外，使用的调度标识符、 **dispidFDirty**和 **dispidShowSenderPhoto**，您可以实现以下任务：</span><span class="sxs-lookup"><span data-stu-id="7b2ec-120">Additionally, using the dispatch identifiers, **dispidFDirty** and **dispidShowSenderPhoto**, you can achieve the following tasks:</span></span>
  
- [<span data-ttu-id="7b2ec-121">确定某个 Outlook 项目是否已修改但未保存（Outlook 辅助参考）</span><span class="sxs-lookup"><span data-stu-id="7b2ec-121">Determine whether an Outlook item has been modified but not saved (Outlook Auxiliary Reference)</span></span>](how-to-determine-if-outlook-item-has-been-modified-but-not-saved.md)
    
- [<span data-ttu-id="7b2ec-122">指定是否要在 Outlook（Outlook 辅助参考）中显示联系人的图片</span><span class="sxs-lookup"><span data-stu-id="7b2ec-122">Specify whether to display a contact's picture in Outlook (Outlook Auxiliary Reference)</span></span>](https://msdn.microsoft.com/library/office/gg262879.aspx)
    

