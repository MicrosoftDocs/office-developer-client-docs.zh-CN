---
title: CreateParameter 方法 (ADO)
TOCTitle: CreateParameter Method (ADO)
ms:assetid: cf080a0b-75d2-dcdf-2715-10af147358e9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250026(v=office.15)
ms:contentKeyID: 48547799
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231042
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 00a2c5e2eb8613434b80c80e2a51cbf5d1deb644
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605483"
---
# <a name="createparameter-method-ado"></a><span data-ttu-id="47793-102">CreateParameter 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="47793-102">CreateParameter Method (ADO)</span></span>


<span data-ttu-id="47793-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="47793-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="47793-104">用于创建具有指定属性的新 [Parameter](parameter-object-ado.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="47793-104">Creates a new [Parameter](parameter-object-ado.md) object with the specified properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="47793-105">语法</span><span class="sxs-lookup"><span data-stu-id="47793-105">Syntax</span></span>

<span data-ttu-id="47793-106">**设置\*\*\*参数* = *命令*。CreateParameter （*名称*、*类型*、 *Direction*、*大小*、*值\*）</span><span class="sxs-lookup"><span data-stu-id="47793-106">**Set** *parameter* = *command*.CreateParameter (*Name*, *Type*, *Direction*, *Size*, *Value*)</span></span>

<span data-ttu-id="47793-107"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="47793-107"><<<<<<< HEAD</span></span>
## <a name="return-value"></a><span data-ttu-id="47793-108">返回值</span><span class="sxs-lookup"><span data-stu-id="47793-108">Return Value</span></span>
=======
## <a name="return-value"></a><span data-ttu-id="47793-109">返回值</span><span class="sxs-lookup"><span data-stu-id="47793-109">Return value</span></span>
>>>>>>> <span data-ttu-id="47793-110">master</span><span class="sxs-lookup"><span data-stu-id="47793-110">master</span></span>

<span data-ttu-id="47793-111">返回 **Parameter** 对象。</span><span class="sxs-lookup"><span data-stu-id="47793-111">Returns a **Parameter** object.</span></span>

## <a name="parameters"></a><span data-ttu-id="47793-112">参数</span><span class="sxs-lookup"><span data-stu-id="47793-112">Parameters</span></span>

  - <span data-ttu-id="47793-113">*Name*</span><span class="sxs-lookup"><span data-stu-id="47793-113">*Name*</span></span>

  - <span data-ttu-id="47793-p101">可选。 **字符串型** 值，包含 **Parameter** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="47793-p101">Optional. A **String** value that contains the name of the **Parameter** object.</span></span>

  - <span data-ttu-id="47793-116">*Type*</span><span class="sxs-lookup"><span data-stu-id="47793-116">*Type*</span></span>

  - <span data-ttu-id="47793-p102">可选。[DataTypeEnum](datatypeenum.md) 值，指定 **Parameter** 对象的数据类型。</span><span class="sxs-lookup"><span data-stu-id="47793-p102">Optional. A [DataTypeEnum](datatypeenum.md) value that specifies the data type of the **Parameter** object.</span></span>

  - <span data-ttu-id="47793-119">*Direction*</span><span class="sxs-lookup"><span data-stu-id="47793-119">*Direction*</span></span>

  - <span data-ttu-id="47793-p103">可选。[ParameterDirectionEnum](parameterdirectionenum.md) 值，指定 **Parameter** 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="47793-p103">Optional. A [ParameterDirectionEnum](parameterdirectionenum.md) value that specifies the type of **Parameter** object.</span></span>

  - <span data-ttu-id="47793-122">*Size*</span><span class="sxs-lookup"><span data-stu-id="47793-122">*Size*</span></span>

  - <span data-ttu-id="47793-p104">可选。 **长整型** 值，指定参数值的最大长度（字符或字节）。</span><span class="sxs-lookup"><span data-stu-id="47793-p104">Optional. A **Long** value that specifies the maximum length for the parameter value in characters or bytes.</span></span>

  - <span data-ttu-id="47793-125">*Value*</span><span class="sxs-lookup"><span data-stu-id="47793-125">*Value*</span></span>

  - <span data-ttu-id="47793-p105">可选。 **变量型** 值，指定 **Parameter** 对象的值。</span><span class="sxs-lookup"><span data-stu-id="47793-p105">Optional. A **Variant** that specifies the value for the **Parameter** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="47793-128">备注</span><span class="sxs-lookup"><span data-stu-id="47793-128">Remarks</span></span>

<span data-ttu-id="47793-p106">使用 **CreateParameter** 方法可以新建具有指定名称、类型、方向、大写和值的 **Parameter** 对象。在参数中传递的所有值都会写入相应的 **Parameter** 属性。</span><span class="sxs-lookup"><span data-stu-id="47793-p106">Use the **CreateParameter** method to create a new **Parameter** object with a specified name, type, direction, size, and value. Any values you pass in the arguments are written to the corresponding **Parameter** properties.</span></span>

<span data-ttu-id="47793-p107">该方法并不会自动将 **Parameter** 对象追加到 **Command** 对象的 [Parameters](command-object-ado.md) 集合。这将允许您在将 **Parameter** 对象追加到集合时设置 ADO 将验证其值的附加属性。</span><span class="sxs-lookup"><span data-stu-id="47793-p107">This method does not automatically append the **Parameter** object to the **Parameters** collection of a [Command](command-object-ado.md) object. This lets you set additional properties whose values ADO will validate when you append the **Parameter** object to the collection.</span></span>

<span data-ttu-id="47793-133">如果在*Type*参数中指定的可变长度数据类型，您必须将*Size*参数传递或之前将其追加到**Parameters**集合; 设置**参数**对象的[Size](size-property-ado.md)属性否则，将发生错误。</span><span class="sxs-lookup"><span data-stu-id="47793-133">If you specify a variable-length data type in the *Type* argument, you must either pass a *Size* argument or set the [Size](size-property-ado.md) property of the **Parameter** object before appending it to the **Parameters** collection; otherwise, an error occurs.</span></span>

<span data-ttu-id="47793-134">如果在 *Type* 参数中指定数值数据类型（**adNumeric** 或 **adDecimal**），则还必须设置 [NumericScale](numericscale-property-ado.md) 和 [Precision](precision-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="47793-134">If you specify a numeric data type (**adNumeric** or **adDecimal**) in the *Type* argument, then you must also set the [NumericScale](numericscale-property-ado.md) and [Precision](precision-property-ado.md) properties.</span></span>

