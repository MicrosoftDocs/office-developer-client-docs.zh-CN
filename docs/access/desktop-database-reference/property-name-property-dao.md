---
title: Property.Name Property (DAO)
TOCTitle: Name Property
ms:assetid: 0dae15e0-5d2e-3bb4-8a44-98db4a8ce516
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845211(v=office.15)
ms:contentKeyID: 48543225
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 09a5e37bf9874888ca37935db38c98773cb03806
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867298"
---
# <a name="propertyname-property-dao"></a><span data-ttu-id="45b45-102">Property.Name Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="45b45-102">Property.Name Property (DAO)</span></span>


<span data-ttu-id="45b45-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="45b45-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="45b45-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="45b45-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="45b45-107">语法</span><span class="sxs-lookup"><span data-stu-id="45b45-107">Syntax</span></span>

<span data-ttu-id="45b45-108">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="45b45-108">*expression* .Name</span></span>

<span data-ttu-id="45b45-109">*表达式*一个代表**Property**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="45b45-109">*expression* A variable that represents a **Property** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="45b45-110">注解</span><span class="sxs-lookup"><span data-stu-id="45b45-110">Remarks</span></span>

<span data-ttu-id="45b45-111">内置属性的 **Name** 属性始终为只读。</span><span class="sxs-lookup"><span data-stu-id="45b45-111">The **Name** property of a built-in property is always read-only.</span></span>

<span data-ttu-id="45b45-112">**Property** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="45b45-112">The maximum length for the name of a **Property** object is 64 characters.</span></span>

