---
title: 第 8 章： 了解游标和锁定
TOCTitle: 'Chapter 8: Understanding cursors and locks'
ms:assetid: 889356f9-53ca-3c46-6781-b37e1f065717
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249598(v=office.15)
ms:contentKeyID: 48546139
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 3ca76b5635e057251aff845ecf45146e6e0d89a6
ms.sourcegitcommit: 38d0db57580cc5f4a0231c27b1643f8db5431ca3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25936936"
---
# <a name="chapter-8-understanding-cursors-and-locks"></a><span data-ttu-id="11acf-102">第 8 章： 了解游标和锁定</span><span class="sxs-lookup"><span data-stu-id="11acf-102">Chapter 8: Understanding cursors and locks</span></span>

<span data-ttu-id="11acf-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="11acf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="11acf-p101">了解游标的工作方式非常重要，您可以针对应用程序的数据访问需求来选择最佳、最有效的游标类型。如果游标配置欠佳，数据访问操作可能会非常缓慢。</span><span class="sxs-lookup"><span data-stu-id="11acf-p101">It is important to understand how cursors operate so you can select the best and most efficient cursor type for an application's data-access requirements. A less-than-optimal cursor configuration can make data-access operations painfully slow.</span></span>

<span data-ttu-id="11acf-106">ADO **Recordset** 对象的很多功能由游标的类型、位置以及锁定类型决定。</span><span class="sxs-lookup"><span data-stu-id="11acf-106">Many capabilities of the ADO **Recordset** object are determined by the type and location of the cursor, as well as the lock type.</span></span>

<span data-ttu-id="11acf-107">本章包含以下主题：</span><span class="sxs-lookup"><span data-stu-id="11acf-107">This chapter covers the following topics:</span></span>

- [<span data-ttu-id="11acf-108">什么是游标？</span><span class="sxs-lookup"><span data-stu-id="11acf-108">What is a cursor?</span></span>](what-is-a-cursor.md)
- [<span data-ttu-id="11acf-109">游标位置的重要性</span><span class="sxs-lookup"><span data-stu-id="11acf-109">The significance of cursor location</span></span>](the-significance-of-cursor-location.md)
- [<span data-ttu-id="11acf-110">Microsoft Cursor Service for OLE DB</span><span class="sxs-lookup"><span data-stu-id="11acf-110">The Microsoft Cursor Service for OLE DB</span></span>](the-microsoft-cursor-service-for-ole-db.md)
- [<span data-ttu-id="11acf-111">使用 CacheSize</span><span class="sxs-lookup"><span data-stu-id="11acf-111">Using CacheSize</span></span>](using-cachesize.md)
- [<span data-ttu-id="11acf-112">游标和锁定特征</span><span class="sxs-lookup"><span data-stu-id="11acf-112">Cursor and lock characteristics</span></span>](cursor-and-lock-characteristics.md)
- [<span data-ttu-id="11acf-113">类型的游标 (ADO)</span><span class="sxs-lookup"><span data-stu-id="11acf-113">Types of cursors (ADO)</span></span>](types-of-cursors.md)
- [<span data-ttu-id="11acf-114">什么是锁定？(ADO)</span><span class="sxs-lookup"><span data-stu-id="11acf-114">What is a lock? (ADO)</span></span>](what-is-a-lock.md)

