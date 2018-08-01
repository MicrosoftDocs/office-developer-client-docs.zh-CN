---
title: MAPI 对象继承层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3dc0b79f-e346-416d-ac81-42eba6b6d3b2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a03b994a613bbb1f17db3e3220b7e053989c278a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776267"
---
# <a name="mapi-object-inheritance-hierarchy"></a><span data-ttu-id="75e2b-103">MAPI 对象继承层次结构</span><span class="sxs-lookup"><span data-stu-id="75e2b-103">MAPI object inheritance hierarchy</span></span>

<span data-ttu-id="75e2b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="75e2b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="75e2b-105">实现 MAPI 对象的所有接口最终都继承[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)，使对象进行通信的 OLE 接口。</span><span class="sxs-lookup"><span data-stu-id="75e2b-105">All interfaces implemented by MAPI objects ultimately inherit from [IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx), the OLE interface that enables objects to communicate.</span></span> <span data-ttu-id="75e2b-106">大多数界面直接继承**IUnknown**，但某些从其他两个基本接口之一继承： [IMAPIProp: IUnknown](imapipropiunknown.md)或[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="75e2b-106">Most interfaces directly inherit from **IUnknown**, but some inherit from one of two other base interfaces: [IMAPIProp : IUnknown](imapipropiunknown.md) or [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md).</span></span> <span data-ttu-id="75e2b-107">下图显示 MAPI 中的完整继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="75e2b-107">The following illustration shows the complete inheritance hierarchy in MAPI.</span></span>
  
<span data-ttu-id="75e2b-108">**MAPI 继承层次结构**</span><span class="sxs-lookup"><span data-stu-id="75e2b-108">**MAPI inheritance hierarchy**</span></span>
  
<span data-ttu-id="75e2b-109">![MAPI 继承层次结构](media/amapi_06.gif "MAPI 继承层次结构")</span><span class="sxs-lookup"><span data-stu-id="75e2b-109">![MAPI inheritance hierarchy](media/amapi_06.gif "MAPI inheritance hierarchy")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75e2b-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75e2b-110">See also</span></span>

- [<span data-ttu-id="75e2b-111">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="75e2b-111">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md) 
- [<span data-ttu-id="75e2b-112">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="75e2b-112">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)
- [<span data-ttu-id="75e2b-113">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="75e2b-113">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

