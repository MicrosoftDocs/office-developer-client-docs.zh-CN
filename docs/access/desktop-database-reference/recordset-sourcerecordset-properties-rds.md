---
title: Recordset、SourceRecordset 属性 (RDS)
TOCTitle: Recordset, SourceRecordset Properties (RDS)
ms:assetid: 5f4bb72d-ddfa-41c0-c353-b3a6632b4a91
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249345(v=office.15)
ms:contentKeyID: 48545160
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a66e803738c16d291817eb80e7f680ff9c3c71e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467019"
---
# <a name="recordset-sourcerecordset-properties-rds"></a><span data-ttu-id="514bc-102">Recordset、SourceRecordset 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="514bc-102">Recordset, SourceRecordset Properties (RDS)</span></span>


<span data-ttu-id="514bc-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="514bc-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="514bc-104">指示从自定义业务对象返回的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="514bc-104">Indicates the **Recordset** object returned from a custom business object.</span></span>

## <a name="syntax"></a><span data-ttu-id="514bc-105">语法</span><span class="sxs-lookup"><span data-stu-id="514bc-105">Syntax</span></span>

<span data-ttu-id="514bc-106">*DataControl*。SourceRecordset = *Recordset*</span><span class="sxs-lookup"><span data-stu-id="514bc-106">*DataControl*.SourceRecordset = *Recordset*</span></span>

<span data-ttu-id="514bc-107">*Recordset* = *DataControl*。记录集</span><span class="sxs-lookup"><span data-stu-id="514bc-107">*Recordset* = *DataControl*.Recordset</span></span>

## <a name="parameters"></a><span data-ttu-id="514bc-108">参数</span><span class="sxs-lookup"><span data-stu-id="514bc-108">Parameters</span></span>

  - <span data-ttu-id="514bc-109">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="514bc-109">*DataControl*</span></span>

  - <span data-ttu-id="514bc-110">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="514bc-110">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="514bc-111">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="514bc-111">*Recordset*</span></span>

  - <span data-ttu-id="514bc-112">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="514bc-112">An object variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="514bc-113">备注</span><span class="sxs-lookup"><span data-stu-id="514bc-113">Remarks</span></span>

<span data-ttu-id="514bc-114">可以将 **SourceRecordset** 属性设置为从自定义业务对象返回的 [Recordset](recordset-object-ado.md)。</span><span class="sxs-lookup"><span data-stu-id="514bc-114">You can set the **SourceRecordset** property to a [Recordset](recordset-object-ado.md) returned from a custom business object.</span></span>

<span data-ttu-id="514bc-p101">这些属性允许应用程序通过自定义进程处理绑定进程。这些属性接收的行集包装在 **Recordset** 中，因此可以直接与 **Recordset** 进行交互，同时可执行设置属性或遍历 **Recordset** 等操作。</span><span class="sxs-lookup"><span data-stu-id="514bc-p101">These properties allow an application to handle the binding process by means of a custom process. They receive a rowset wrapped in a **Recordset** so that you can interact directly with the **Recordset**, performing actions such as setting properties or iterating through the **Recordset**.</span></span>

<span data-ttu-id="514bc-117">可以设置 **SourceRecordset** 属性，也可以在运行时在脚本代码中读取 **Recordset** 属性。</span><span class="sxs-lookup"><span data-stu-id="514bc-117">You can set the **SourceRecordset** property or read the **Recordset** property at run time in scripting code.</span></span>

<span data-ttu-id="514bc-118">**SourceRecordset** 为只写属性，与 **Recordset** 属性恰恰相反，后者为只读属性。</span><span class="sxs-lookup"><span data-stu-id="514bc-118">**SourceRecordset** is a write-only property, in contrast to the **Recordset** property, which is a read-only property.</span></span>

