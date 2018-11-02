---
title: Flush 方法-ActiveX 数据对象 (ADO)
TOCTitle: Flush method (ADO)
ms:assetid: c167e3b1-c133-ce45-6cee-5a1280a1568f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249941(v=office.15)
ms:contentKeyID: 48547529
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b52bb3d595c21ccc682e5af182b794065bcd1b13
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25920443"
---
# <a name="flush-method-ado"></a><span data-ttu-id="af578-102">Flush 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="af578-102">Flush method (ADO)</span></span>


<span data-ttu-id="af578-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="af578-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="af578-104">用于将保留在 ADO 缓冲区中的 [Stream](stream-object-ado.md) 的内容强制转移到 **Stream** 所关联的基础对象中。</span><span class="sxs-lookup"><span data-stu-id="af578-104">Forces the contents of the [Stream](stream-object-ado.md) remaining in the ADO buffer to the underlying object with which the **Stream** is associated.</span></span>

## <a name="syntax"></a><span data-ttu-id="af578-105">语法</span><span class="sxs-lookup"><span data-stu-id="af578-105">Syntax</span></span>

<span data-ttu-id="af578-106">*流*。刷新</span><span class="sxs-lookup"><span data-stu-id="af578-106">*Stream*.Flush</span></span>

## <a name="remarks"></a><span data-ttu-id="af578-107">备注</span><span class="sxs-lookup"><span data-stu-id="af578-107">Remarks</span></span>

<span data-ttu-id="af578-p101">该方法可用于将流缓冲区的内容发送到基础对象（例如，由 URL 表示的作为 **Stream** 对象的源的节点或文件）。当您希望确保已写入对 **Stream** 内容所做的所有更改时，应调用该方法。不过，使用 ADO 时，通常不需要调用 **Flush** ，因为 ADO 会在后台尽可能地持续刷新其缓冲区。对 **Stream** 内容的更改是自动进行的，且直到调用 **Flush** 时才进行缓存。</span><span class="sxs-lookup"><span data-stu-id="af578-p101">This method may be used to send the contents of the stream buffer to the underlying object (for example, the node or file represented by the URL that is the source of the **Stream** object). This method should be called when you want to ensure that all changes made to the contents of a **Stream** have been written. However, with ADO it is not usually necessary to call **Flush**, as ADO continuously flushes its buffer as much as possible in the background. Changes to the content of a **Stream** are made automatically, not cached until **Flush** is called.</span></span>

<span data-ttu-id="af578-112">使用 **Close** 方法关闭 [Stream](close-method-ado.md) 将自动刷新 **Stream** 的内容；在马上要 **关闭** 流之前不需要显式调用 **Flush** 。</span><span class="sxs-lookup"><span data-stu-id="af578-112">Closing a **Stream** with the [Close](close-method-ado.md) method flushes the contents of a **Stream** automatically; there is no need to explicitly call **Flush** immediately before **Close**.</span></span>

