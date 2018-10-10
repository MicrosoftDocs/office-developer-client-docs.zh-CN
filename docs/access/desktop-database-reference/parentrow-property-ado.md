---
title: ParentRow 属性 (ADO)
TOCTitle: ParentRow Property (ADO)
ms:assetid: c7520353-9428-9c8f-9d21-ff42e30e1193
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249971(v=office.15)
ms:contentKeyID: 48547638
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 834dcaed7d1acdcf66410584436e2ccee8c91c56
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25469004"
---
# <a name="parentrow-property-ado"></a><span data-ttu-id="4ae06-102">ParentRow 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="4ae06-102">ParentRow Property (ADO)</span></span>


<span data-ttu-id="4ae06-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4ae06-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="4ae06-104">在 **ADORecordConstruction** 对象上设置 OLE DB **Row** 对象的容器，以便将行的父项转换为 ADO **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="4ae06-104">Sets the container of an OLE DB **Row** object on an **ADORecordConstruction** object, so that the parent of the row is turned into an ADO **Record** object.</span></span>

<span data-ttu-id="4ae06-105">为只写属性。</span><span class="sxs-lookup"><span data-stu-id="4ae06-105">Write-only.</span></span>

## <a name="syntax"></a><span data-ttu-id="4ae06-106">语法</span><span class="sxs-lookup"><span data-stu-id="4ae06-106">Syntax</span></span>

<span data-ttu-id="4ae06-107">HRESULT 放置\_ParentRow (\[的\]IUnknown\* pParent);</span><span class="sxs-lookup"><span data-stu-id="4ae06-107">HRESULT put\_ParentRow(\[in\] IUnknown\* pParent);</span></span>

## <a name="parameters"></a><span data-ttu-id="4ae06-108">参数</span><span class="sxs-lookup"><span data-stu-id="4ae06-108">Parameters</span></span>

  - <span data-ttu-id="4ae06-109">*pParent*</span><span class="sxs-lookup"><span data-stu-id="4ae06-109">*pParent*</span></span>

  - <span data-ttu-id="4ae06-110">行的容器。</span><span class="sxs-lookup"><span data-stu-id="4ae06-110">A container of a row.</span></span>

## <a name="return-values"></a><span data-ttu-id="4ae06-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4ae06-111">Return Values</span></span>

<span data-ttu-id="4ae06-112">此属性方法返回标准 HRESULT 值，包括 S\_确定和 E\_失败。</span><span class="sxs-lookup"><span data-stu-id="4ae06-112">This property method returns the standard HRESULT values, including S\_OK and E\_FAIL.</span></span>

## <a name="applies-to"></a><span data-ttu-id="4ae06-113">应用于</span><span class="sxs-lookup"><span data-stu-id="4ae06-113">Applies To</span></span>

[<span data-ttu-id="4ae06-114">ADORecordConstruction</span><span class="sxs-lookup"><span data-stu-id="4ae06-114">ADORecordConstruction</span></span>](adorecordconstruction-interface-ado.md)

