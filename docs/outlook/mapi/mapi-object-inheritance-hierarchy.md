---
title: MAPI 对象继承层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3dc0b79f-e346-416d-ac81-42eba6b6d3b2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4b610415089ff19165ffcabc9e13901ed63c907d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345836"
---
# <a name="mapi-object-inheritance-hierarchy"></a><span data-ttu-id="111d1-103">MAPI 对象继承层次结构</span><span class="sxs-lookup"><span data-stu-id="111d1-103">MAPI object inheritance hierarchy</span></span>

<span data-ttu-id="111d1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="111d1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="111d1-105">MAPI 对象实现的所有接口最终都继承自 [IUnknown，](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)即允许对象进行通信的 OLE 接口。</span><span class="sxs-lookup"><span data-stu-id="111d1-105">All interfaces implemented by MAPI objects ultimately inherit from [IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx), the OLE interface that enables objects to communicate.</span></span> <span data-ttu-id="111d1-106">大多数接口直接继承自 **IUnknown，** 但一些接口继承自其他两个基接口之一 [：IMAPIProp ： IUnknown](imapipropiunknown.md) 或 [IMAPIContainer ： IMAPIProp](imapicontainerimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="111d1-106">Most interfaces directly inherit from **IUnknown**, but some inherit from one of two other base interfaces: [IMAPIProp : IUnknown](imapipropiunknown.md) or [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md).</span></span> <span data-ttu-id="111d1-107">下图显示了 MAPI 中的完整继承层次结构。</span><span class="sxs-lookup"><span data-stu-id="111d1-107">The following illustration shows the complete inheritance hierarchy in MAPI.</span></span>
  
<span data-ttu-id="111d1-108">**MAPI 继承层次结构**</span><span class="sxs-lookup"><span data-stu-id="111d1-108">**MAPI inheritance hierarchy**</span></span>
  
<span data-ttu-id="111d1-109">![MAPI 继承层次结构](media/amapi_06.gif "MAPI 继承层次结构")</span><span class="sxs-lookup"><span data-stu-id="111d1-109">![MAPI inheritance hierarchy](media/amapi_06.gif "MAPI inheritance hierarchy")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="111d1-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="111d1-110">See also</span></span>

- [<span data-ttu-id="111d1-111">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="111d1-111">IMAPIProp : IUnknown</span></span>](imapipropiunknown.md) 
- [<span data-ttu-id="111d1-112">IMAPIContainer : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="111d1-112">IMAPIContainer : IMAPIProp</span></span>](imapicontainerimapiprop.md)
- [<span data-ttu-id="111d1-113">MAPI 对象和接口概述</span><span class="sxs-lookup"><span data-stu-id="111d1-113">MAPI Object and Interface Overview</span></span>](mapi-object-and-interface-overview.md)

