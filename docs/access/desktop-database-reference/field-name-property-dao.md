---
title: Field.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: b7093c63-6d57-31c8-5845-d65250386d0f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822416(v=office.15)
ms:contentKeyID: 48547292
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: f84ccf11069e98fb6a7183cc996f993e8d6ebb75
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293075"
---
# <a name="fieldname-property-dao"></a><span data-ttu-id="f6483-102">Field.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="f6483-102">Field.Name property (DAO)</span></span>


<span data-ttu-id="f6483-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f6483-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f6483-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="f6483-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6483-107">语法</span><span class="sxs-lookup"><span data-stu-id="f6483-107">Syntax</span></span>

<span data-ttu-id="f6483-108">*表达式*。别名</span><span class="sxs-lookup"><span data-stu-id="f6483-108">*expression* .Name</span></span>

<span data-ttu-id="f6483-109">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f6483-109">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6483-110">注解</span><span class="sxs-lookup"><span data-stu-id="f6483-110">Remarks</span></span>

<span data-ttu-id="f6483-111">**Field** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="f6483-111">The maximum length for the name of a **Field** object is 64 characters.</span></span>

