---
title: ParentRow 属性 (ADO)
TOCTitle: ParentRow property (ADO)
ms:assetid: c7520353-9428-9c8f-9d21-ff42e30e1193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249971(v=office.15)
ms:contentKeyID: 48547638
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2844f7c93164c4b384a895cd32a13bd682154ce3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287736"
---
# <a name="parentrow-property-ado"></a><span data-ttu-id="0360c-102">ParentRow 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="0360c-102">ParentRow property (ADO)</span></span>

<span data-ttu-id="0360c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0360c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0360c-104">在 **ADORecordConstruction** 对象上设置 OLE DB **Row** 对象的容器，以便将行的父项转换为 ADO **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="0360c-104">Sets the container of an OLE DB **Row** object on an **ADORecordConstruction** object, so that the parent of the row is turned into an ADO **Record** object.</span></span>

<span data-ttu-id="0360c-105">为只写属性。</span><span class="sxs-lookup"><span data-stu-id="0360c-105">Write-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="0360c-106">语法</span><span class="sxs-lookup"><span data-stu-id="0360c-106">Syntax</span></span>

<span data-ttu-id="0360c-107">HRESULT put\_ParentRow (\[在\] IUnknown\* pParent 中);</span><span class="sxs-lookup"><span data-stu-id="0360c-107">HRESULT put\_ParentRow(\[in\] IUnknown\* pParent);</span></span>

## <a name="parameters"></a><span data-ttu-id="0360c-108">参数</span><span class="sxs-lookup"><span data-stu-id="0360c-108">Parameters</span></span>

|<span data-ttu-id="0360c-109">参数</span><span class="sxs-lookup"><span data-stu-id="0360c-109">Parameter</span></span>|<span data-ttu-id="0360c-110">描述</span><span class="sxs-lookup"><span data-stu-id="0360c-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="0360c-111">*pParent*</span><span class="sxs-lookup"><span data-stu-id="0360c-111">*pParent*</span></span> |<span data-ttu-id="0360c-112">行的容器。</span><span class="sxs-lookup"><span data-stu-id="0360c-112">A container of a row.</span></span>|

## <a name="return-values"></a><span data-ttu-id="0360c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="0360c-113">Return values</span></span>

<span data-ttu-id="0360c-114">此属性方法返回标准的 HRESULT 值, 包括 S\_OK 和 E\_FAIL。</span><span class="sxs-lookup"><span data-stu-id="0360c-114">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="0360c-115">适用于</span><span class="sxs-lookup"><span data-stu-id="0360c-115">Applies to</span></span>

[<span data-ttu-id="0360c-116">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="0360c-116">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

