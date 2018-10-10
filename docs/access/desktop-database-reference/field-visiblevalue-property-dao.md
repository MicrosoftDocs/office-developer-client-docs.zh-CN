---
title: Field.VisibleValue Property (DAO)
TOCTitle: VisibleValue Property
ms:assetid: e40fcb43-9a1d-69e7-1544-8f15ef21daf4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835776(v=office.15)
ms:contentKeyID: 48548332
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 892c7b41a692f353ee7e5bdd2191f6e21b8b4cf2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466285"
---
# <a name="fieldvisiblevalue-property-dao"></a><span data-ttu-id="a8d21-102">Field.VisibleValue Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="a8d21-102">Field.VisibleValue Property (DAO)</span></span>


<span data-ttu-id="a8d21-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="a8d21-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="a8d21-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8d21-104">Syntax</span></span>

<span data-ttu-id="a8d21-105">*表达式*。VisibleValue</span><span class="sxs-lookup"><span data-stu-id="a8d21-105">*expression* .VisibleValue</span></span>

<span data-ttu-id="a8d21-106">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="a8d21-106">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8d21-107">注解</span><span class="sxs-lookup"><span data-stu-id="a8d21-107">Remarks</span></span>

<span data-ttu-id="a8d21-p101">该属性包含的字段值当前位于服务器上的数据库中。在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。如果发生这种情况，则可以通过该属性访问第二个客户端设置的值。</span><span class="sxs-lookup"><span data-stu-id="a8d21-p101">This property contains the value of the field that is currently in the database on the server. During an optimistic batch update, a collision may occur where a second client modified the same field and record in between the time the first client retrieved the data and the first client's update attempt. When this happens, the value that the second client set will be accessible through this property.</span></span>

