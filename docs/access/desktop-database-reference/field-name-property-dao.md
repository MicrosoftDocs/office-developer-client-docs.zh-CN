---
title: Field.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: b7093c63-6d57-31c8-5845-d65250386d0f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822416(v=office.15)
ms:contentKeyID: 48547292
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 72de5b4acdeed8736dea7857e412ee916cf308dd
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919197"
---
# <a name="fieldname-property-dao"></a><span data-ttu-id="1a8b9-102">Field.Name 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="1a8b9-102">Field.Name property (DAO)</span></span>


<span data-ttu-id="1a8b9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="1a8b9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="1a8b9-p101">返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。</span><span class="sxs-lookup"><span data-stu-id="1a8b9-p101">Returns or sets the name of the specified object. Read/write **String** if the object has not been appended to a collection. Read-only **String** if the object has been appended to a collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="1a8b9-107">语法</span><span class="sxs-lookup"><span data-stu-id="1a8b9-107">Syntax</span></span>

<span data-ttu-id="1a8b9-108">*表达式*。名称</span><span class="sxs-lookup"><span data-stu-id="1a8b9-108">*expression* .Name</span></span>

<span data-ttu-id="1a8b9-109">*表达式*一个代表**Field**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="1a8b9-109">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a8b9-110">注解</span><span class="sxs-lookup"><span data-stu-id="1a8b9-110">Remarks</span></span>

<span data-ttu-id="1a8b9-111">**Field** 对象名称的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="1a8b9-111">The maximum length for the name of a **Field** object is 64 characters.</span></span>

