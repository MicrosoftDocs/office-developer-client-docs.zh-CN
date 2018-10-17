---
title: Field2.VisibleValue Property (DAO)
TOCTitle: VisibleValue Property
ms:assetid: 1e023a1a-fd49-7570-42bd-2f4c06ac5e5e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845809(v=office.15)
ms:contentKeyID: 48543611
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101184
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9c901045f1f856142a628fb31806610e7d5dce43
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465909"
---
# <a name="field2visiblevalue-property-dao"></a><span data-ttu-id="f4b93-102">Field2.VisibleValue Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f4b93-102">Field2.VisibleValue Property (DAO)</span></span>


<span data-ttu-id="f4b93-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f4b93-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="f4b93-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4b93-104">Syntax</span></span>

<span data-ttu-id="f4b93-105">*表达式*。VisibleValue</span><span class="sxs-lookup"><span data-stu-id="f4b93-105">*expression* .VisibleValue</span></span>

<span data-ttu-id="f4b93-106">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f4b93-106">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4b93-107">注解</span><span class="sxs-lookup"><span data-stu-id="f4b93-107">Remarks</span></span>

<span data-ttu-id="f4b93-p101">该属性包含的字段值当前位于服务器上的数据库中。在乐观批更新过程中，如果在第一个客户端检索完数据但尚未进行更新尝试时，第二个客户端修改了相同的字段和记录，则会发生冲突。如果发生这种情况，则可以通过该属性访问第二个客户端设置的值。</span><span class="sxs-lookup"><span data-stu-id="f4b93-p101">This property contains the value of the field that is currently in the database on the server. During an optimistic batch update, a collision may occur where a second client modified the same field and record in between the time the first client retrieved the data and the first client's update attempt. When this happens, the value that the second client set will be accessible through this property.</span></span>
