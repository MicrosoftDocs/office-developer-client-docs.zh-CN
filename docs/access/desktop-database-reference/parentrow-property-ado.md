---
title: ParentRow 属性 (ADO)
TOCTitle: ParentRow property (ADO)
ms:assetid: c7520353-9428-9c8f-9d21-ff42e30e1193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249971(v=office.15)
ms:contentKeyID: 48547638
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 06bb1110dfa7e7a055fa6cd863dcd2cc17f3f585
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25950145"
---
# <a name="parentrow-property-ado"></a><span data-ttu-id="8be8a-102">ParentRow 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="8be8a-102">ParentRow property (ADO)</span></span>

<span data-ttu-id="8be8a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8be8a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8be8a-104">在 **ADORecordConstruction** 对象上设置 OLE DB **Row** 对象的容器，以便将行的父项转换为 ADO **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="8be8a-104">Sets the container of an OLE DB **Row** object on an **ADORecordConstruction** object, so that the parent of the row is turned into an ADO **Record** object.</span></span>

<span data-ttu-id="8be8a-105">为只写属性。</span><span class="sxs-lookup"><span data-stu-id="8be8a-105">Write-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="8be8a-106">语法</span><span class="sxs-lookup"><span data-stu-id="8be8a-106">Syntax</span></span>

<span data-ttu-id="8be8a-107">HRESULT 放置\_ParentRow (\[的\]IUnknown\* pParent);</span><span class="sxs-lookup"><span data-stu-id="8be8a-107">HRESULT put\_ParentRow(\[in\] IUnknown\* pParent);</span></span>

## <a name="parameters"></a><span data-ttu-id="8be8a-108">参数</span><span class="sxs-lookup"><span data-stu-id="8be8a-108">Parameters</span></span>

|<span data-ttu-id="8be8a-109">参数</span><span class="sxs-lookup"><span data-stu-id="8be8a-109">Parameter</span></span>|<span data-ttu-id="8be8a-110">说明</span><span class="sxs-lookup"><span data-stu-id="8be8a-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="8be8a-111">*pParent*</span><span class="sxs-lookup"><span data-stu-id="8be8a-111">*pParent*</span></span> |<span data-ttu-id="8be8a-112">行的容器。</span><span class="sxs-lookup"><span data-stu-id="8be8a-112">A container of a row.</span></span>|

## <a name="return-values"></a><span data-ttu-id="8be8a-113">返回值</span><span class="sxs-lookup"><span data-stu-id="8be8a-113">Return values</span></span>

<span data-ttu-id="8be8a-114">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="8be8a-114">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="8be8a-115">适用于</span><span class="sxs-lookup"><span data-stu-id="8be8a-115">Applies to</span></span>

[<span data-ttu-id="8be8a-116">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="8be8a-116">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

