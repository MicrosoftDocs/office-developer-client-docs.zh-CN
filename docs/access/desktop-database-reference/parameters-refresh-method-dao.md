---
title: Parameters.Refresh 方法 (DAO)
TOCTitle: Refresh Method
ms:assetid: 47db1602-e223-985d-881c-b73e2d26acb7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193228(v=office.15)
ms:contentKeyID: 48544607
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5d9deafaf70ac230b2c3a93a1e8100a6300a5cc6
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920926"
---
# <a name="parametersrefresh-method-dao"></a><span data-ttu-id="00963-102">Parameters.Refresh 方法 (DAO)</span><span class="sxs-lookup"><span data-stu-id="00963-102">Parameters.Refresh method (DAO)</span></span>


<span data-ttu-id="00963-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="00963-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="00963-104">更新指定集合中的对象，以反映数据库的当前架构。</span><span class="sxs-lookup"><span data-stu-id="00963-104">Updates the objects in the specified colletion to reflect the database's current schema.</span></span>

## <a name="syntax"></a><span data-ttu-id="00963-105">语法</span><span class="sxs-lookup"><span data-stu-id="00963-105">Syntax</span></span>

<span data-ttu-id="00963-106">*表达式*。刷新</span><span class="sxs-lookup"><span data-stu-id="00963-106">*expression* .Refresh</span></span>

<span data-ttu-id="00963-107">*表达式*一个代表**Parameters**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="00963-107">*expression* A variable that represents a **Parameters** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="00963-108">注解</span><span class="sxs-lookup"><span data-stu-id="00963-108">Remarks</span></span>

<span data-ttu-id="00963-p101">在其他用户可以更改数据库的多用户环境中使用 **Refresh** 方法。对于间接地受数据库更改影响的任何集合，可能也需要使用此方法。例如，如果更改了 **Users** 集合，则在使用 **Groups** 集合之前，可能需要刷新 **Groups** 集合。</span><span class="sxs-lookup"><span data-stu-id="00963-p101">Use the **Refresh** method in multiuser environments in which other users may change the database. You may also need to use it on any collections that are indirectly affected by changes to the database. For example, if you change a **Users** collection, you may need to refresh a **Groups** collection before using the **Groups** collection.</span></span>

<span data-ttu-id="00963-p102">首次引用一个集合时，将使用对象填充此集合，并且此集合不会自动反映其他用户所做的后续更改。如果另一个用户有可能更改了某个集合，请立即对此集合使用 Refresh 方法，然后在应用程序中执行假定集合中存在或缺少特定对象的任务。这可以确保集合尽可能地处于最新状态。但另一方面，使用 Refresh 可能减慢性能，这是您不想看到的。</span><span class="sxs-lookup"><span data-stu-id="00963-p102">A collection is filled with objects the first time it's referred to and won't automatically reflect subsequent changes other users make. If it's likely that another user has changed a collection, use the Refresh method on the collection immediately before carrying out any task in your application that assumes the presence or absence of a particular object in the collection. This will ensure that the collection is as up-to-date as possible. On the other hand, using Refresh can unnecessarily slow performance.</span></span>

