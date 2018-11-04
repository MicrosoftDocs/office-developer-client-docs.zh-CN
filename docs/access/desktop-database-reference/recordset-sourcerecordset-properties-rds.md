---
title: Recordset、SourceRecordset 属性 (RDS)
TOCTitle: Recordset, SourceRecordset properties (RDS)
ms:assetid: 5f4bb72d-ddfa-41c0-c353-b3a6632b4a91
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249345(v=office.15)
ms:contentKeyID: 48545160
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 21176e050c77b0f14fcb03b054e8a1ab692df7d5
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949255"
---
# <a name="recordset-sourcerecordset-properties-rds"></a><span data-ttu-id="93ea9-102">Recordset、SourceRecordset 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="93ea9-102">Recordset, SourceRecordset properties (RDS)</span></span>

<span data-ttu-id="93ea9-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="93ea9-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="93ea9-104">指示从自定义业务对象返回的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="93ea9-104">Indicates the **Recordset** object returned from a custom business object.</span></span>

## <a name="syntax"></a><span data-ttu-id="93ea9-105">语法</span><span class="sxs-lookup"><span data-stu-id="93ea9-105">Syntax</span></span>

<span data-ttu-id="93ea9-106">*DataControl*。SourceRecordset = *Recordset*</span><span class="sxs-lookup"><span data-stu-id="93ea9-106">*DataControl*.SourceRecordset = *Recordset*</span></span>

<span data-ttu-id="93ea9-107">*Recordset* = *DataControl*。记录集</span><span class="sxs-lookup"><span data-stu-id="93ea9-107">*Recordset* = *DataControl*.Recordset</span></span>

## <a name="parameters"></a><span data-ttu-id="93ea9-108">参数</span><span class="sxs-lookup"><span data-stu-id="93ea9-108">Parameters</span></span>

|<span data-ttu-id="93ea9-109">参数</span><span class="sxs-lookup"><span data-stu-id="93ea9-109">Parameter</span></span>|<span data-ttu-id="93ea9-110">说明</span><span class="sxs-lookup"><span data-stu-id="93ea9-110">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="93ea9-111">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="93ea9-111">*DataControl*</span></span> |<span data-ttu-id="93ea9-112">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="93ea9-112">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="93ea9-113">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="93ea9-113">*Recordset*</span></span> |<span data-ttu-id="93ea9-114">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="93ea9-114">An object variable that represents a **Recordset** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="93ea9-115">备注</span><span class="sxs-lookup"><span data-stu-id="93ea9-115">Remarks</span></span>

<span data-ttu-id="93ea9-116">可以将 **SourceRecordset** 属性设置为从自定义业务对象返回的 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="93ea9-116">You can set the **SourceRecordset** property to a [Recordset](recordset-object-ado.md) returned from a custom business object.</span></span>

<span data-ttu-id="93ea9-p101">这些属性允许应用程序通过自定义进程处理绑定进程。这些属性接收的行集包装在 **Recordset** 中，因此可以直接与 **Recordset** 进行交互，同时可执行设置属性或遍历 **Recordset** 等操作。</span><span class="sxs-lookup"><span data-stu-id="93ea9-p101">These properties allow an application to handle the binding process by means of a custom process. They receive a rowset wrapped in a **Recordset** so that you can interact directly with the **Recordset**, performing actions such as setting properties or iterating through the **Recordset**.</span></span>

<span data-ttu-id="93ea9-119">可以设置 **SourceRecordset** 属性，也可以在运行时在脚本代码中读取 **Recordset** 属性。</span><span class="sxs-lookup"><span data-stu-id="93ea9-119">You can set the **SourceRecordset** property or read the **Recordset** property at run time in scripting code.</span></span>

<span data-ttu-id="93ea9-120">**SourceRecordset** 为只写属性，与 **Recordset** 属性恰恰相反，后者为只读属性。</span><span class="sxs-lookup"><span data-stu-id="93ea9-120">**SourceRecordset** is a write-only property, in contrast to the **Recordset** property, which is a read-only property.</span></span>

