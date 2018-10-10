---
title: Field.Name Property (DAO)
TOCTitle: Name Property
ms:assetid: b7093c63-6d57-31c8-5845-d65250386d0f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822416(v=office.15)
ms:contentKeyID: 48547292
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9f55300dda0180da5116b95194b6b6c5710c6383
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465732"
---
# <a name="fieldname-property-dao"></a><span data-ttu-id="24b02-102">Field.Name Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="24b02-102">Field.Name Property (DAO)</span></span>


<span data-ttu-id="24b02-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="24b02-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="24b02-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="24b02-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="24b02-107">语法</span><span class="sxs-lookup"><span data-stu-id="24b02-107">Syntax</span></span>

<span data-ttu-id="24b02-108">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="24b02-108">*expression* .Name</span></span>

<span data-ttu-id="24b02-109">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="24b02-109">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="24b02-110">注解</span><span class="sxs-lookup"><span data-stu-id="24b02-110">Remarks</span></span>

<span data-ttu-id="24b02-111">**Field** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="24b02-111">The maximum length for the name of a **Field** object is 64 characters.</span></span>

