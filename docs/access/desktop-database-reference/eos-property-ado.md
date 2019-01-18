---
title: EOS 属性 (ADO-访问桌面数据库参考 （英文）)）
TOCTitle: EOS property (ADO)
ms:assetid: 97cd23ef-cca8-4dcc-2641-082a0e1b853c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249676(v=office.15)
ms:contentKeyID: 48546474
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a35503fb0ad320e82ed385c7014b2a18de586064
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28716598"
---
# <a name="eos-property-ado"></a><span data-ttu-id="a284d-102">EOS 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a284d-102">EOS property (ADO)</span></span>


<span data-ttu-id="a284d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a284d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a284d-104">指示当前位置是否位于流的末尾。</span><span class="sxs-lookup"><span data-stu-id="a284d-104">Indicates whether the current position is at the end of the stream.</span></span>

## <a name="return-values"></a><span data-ttu-id="a284d-105">返回值</span><span class="sxs-lookup"><span data-stu-id="a284d-105">Return values</span></span>

<span data-ttu-id="a284d-p101">返回一个 **Boolean** 值，以指示当前位置是否位于流的末尾。如果流中没有更多的字节， **EOS** 将返回 **True** ；如果当前位置后还有字节，它将返回 **False** 。</span><span class="sxs-lookup"><span data-stu-id="a284d-p101">Returns a **Boolean** value that indicates whether the current position is at the end of the stream. **EOS** returns **True** if there are no more bytes in the stream; it returns **False** if there are more bytes following the current position.</span></span>

<span data-ttu-id="a284d-p102">若要设置流位置的末尾位置，请使用 [SetEOS](seteos-method-ado.md) 方法。若要确定当前位置，请使用 [Position](position-property-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="a284d-p102">To set the end of stream position, use the [SetEOS](seteos-method-ado.md) method. To determine the current position, use the [Position](position-property-ado.md) property.</span></span>

