---
title: Field.VisibleValue 属性 (DAO)
TOCTitle: VisibleValue Property
ms:assetid: e40fcb43-9a1d-69e7-1544-8f15ef21daf4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835776(v=office.15)
ms:contentKeyID: 48548332
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 461b8c43bf9000e5ecde3a3676cebf54be8e4166
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927569"
---
# <a name="fieldvisiblevalue-property-dao"></a><span data-ttu-id="79e30-102">Field.VisibleValue 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="79e30-102">Field.VisibleValue property (DAO)</span></span>


<span data-ttu-id="79e30-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="79e30-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="79e30-104">语法</span><span class="sxs-lookup"><span data-stu-id="79e30-104">Syntax</span></span>

<span data-ttu-id="79e30-105">*表达式*。VisibleValue</span><span class="sxs-lookup"><span data-stu-id="79e30-105">*expression* .VisibleValue</span></span>

<span data-ttu-id="79e30-106">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="79e30-106">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="79e30-107">注解</span><span class="sxs-lookup"><span data-stu-id="79e30-107">Remarks</span></span>

<span data-ttu-id="79e30-p101">该属性包含的字段值当前位于服务器上的数据库中。在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。如果发生这种情况，则可以通过该属性访问第二个客户端设置的值。</span><span class="sxs-lookup"><span data-stu-id="79e30-p101">This property contains the value of the field that is currently in the database on the server. During an optimistic batch update, a collision may occur where a second client modified the same field and record in between the time the first client retrieved the data and the first client's update attempt. When this happens, the value that the second client set will be accessible through this property.</span></span>

