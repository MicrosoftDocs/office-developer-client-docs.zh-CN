---
title: Field2.OriginalValue Property (DAO)
TOCTitle: OriginalValue Property
ms:assetid: 10fed55e-c938-2ae6-8fd2-996745a63da3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845353(v=office.15)
ms:contentKeyID: 48543306
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101183
f1_categories:
- Office.Version=v15
ms.openlocfilehash: a08612076ba138e5e181eec80bec2350fe27ec86
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468771"
---
# <a name="field2originalvalue-property-dao"></a><span data-ttu-id="812c4-102">Field2.OriginalValue Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="812c4-102">Field2.OriginalValue Property (DAO)</span></span>


<span data-ttu-id="812c4-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="812c4-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="812c4-104">语法</span><span class="sxs-lookup"><span data-stu-id="812c4-104">Syntax</span></span>

<span data-ttu-id="812c4-105">*表达式*。OriginalValue</span><span class="sxs-lookup"><span data-stu-id="812c4-105">*expression* .OriginalValue</span></span>

<span data-ttu-id="812c4-106">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="812c4-106">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="812c4-107">注解</span><span class="sxs-lookup"><span data-stu-id="812c4-107">Remarks</span></span>

<span data-ttu-id="812c4-p101">在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。 **OriginalValue** 属性包含上一个批 **Update** 开始时的字段值。如果该值与批 **Update** 尝试写入数据库时数据库中的实际值不匹配，则会发生冲突。如果发生这种情况，可通过 **VisibleValue** 属性访问数据库中的新值。</span><span class="sxs-lookup"><span data-stu-id="812c4-p101">During an optimistic batch update, a collision may occur where a second client modifies the same field and record in between the time the first client retrieves the data and the first client's update attempt. The **OriginalValue** property contains the value of the field at the time the last batch **Update** began. If this value does not match the value actually in the database when the batch **Update** attempts to write to the database, a collision occurs. When this happens, the new value in the database will be accessible through the **VisibleValue** property.</span></span>
