---
title: Property.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: 0dae15e0-5d2e-3bb4-8a44-98db4a8ce516
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845211(v=office.15)
ms:contentKeyID: 48543225
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa552a477ad6b9f047f3fd2231e4b0ba8d26c1ce
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302901"
---
# <a name="propertyname-property-dao"></a><span data-ttu-id="12a59-102">Property.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="12a59-102">Property.Name property (DAO)</span></span>


<span data-ttu-id="12a59-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="12a59-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="12a59-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="12a59-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="12a59-107">语法</span><span class="sxs-lookup"><span data-stu-id="12a59-107">Syntax</span></span>

<span data-ttu-id="12a59-108">*表达式*。别名</span><span class="sxs-lookup"><span data-stu-id="12a59-108">*expression* .Name</span></span>

<span data-ttu-id="12a59-109">*表达式*一个代表**Property**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="12a59-109">*expression* A variable that represents a **Property** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="12a59-110">注解</span><span class="sxs-lookup"><span data-stu-id="12a59-110">Remarks</span></span>

<span data-ttu-id="12a59-111">内置属性的 **Name** 属性始终为只读。</span><span class="sxs-lookup"><span data-stu-id="12a59-111">The **Name** property of a built-in property is always read-only.</span></span>

<span data-ttu-id="12a59-112">**Property** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="12a59-112">The maximum length for the name of a **Property** object is 64 characters.</span></span>

