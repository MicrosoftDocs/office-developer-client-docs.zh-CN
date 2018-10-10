---
title: SkipLine 方法 (ADO)
TOCTitle: SkipLine Method (ADO)
ms:assetid: 419c24c3-6b84-eed0-5884-f2dcd485dc3d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249187(v=office.15)
ms:contentKeyID: 48544456
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 28cb222a3ed0e5497e03efbb7394081c96b4d4ef
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467249"
---
# <a name="skipline-method-ado"></a><span data-ttu-id="74d41-102">SkipLine 方法 (ADO)</span><span class="sxs-lookup"><span data-stu-id="74d41-102">SkipLine Method (ADO)</span></span>


<span data-ttu-id="74d41-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="74d41-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="74d41-104">用于在读取文本流时跳过一整行。</span><span class="sxs-lookup"><span data-stu-id="74d41-104">Skips one entire line when reading a text stream.</span></span>

## <a name="syntax"></a><span data-ttu-id="74d41-105">语法</span><span class="sxs-lookup"><span data-stu-id="74d41-105">Syntax</span></span>

<span data-ttu-id="74d41-106">*流*。SkipLine</span><span class="sxs-lookup"><span data-stu-id="74d41-106">*Stream*.SkipLine</span></span>

## <a name="remarks"></a><span data-ttu-id="74d41-107">备注</span><span class="sxs-lookup"><span data-stu-id="74d41-107">Remarks</span></span>

<span data-ttu-id="74d41-p101">跳过下一个行分隔符（含）之前的所有字符。默认情况下，[LineSeparator](lineseparator-property-ado.md) 为 **adCRLF** 。如果试图跳过 [EOS](eos-property-ado.md)，则当前位置将只保持在 **EOS** 。</span><span class="sxs-lookup"><span data-stu-id="74d41-p101">All characters up to, and including the next line separator, are skipped. By default, the [LineSeparator](lineseparator-property-ado.md) is **adCRLF**. If you attempt to skip past [EOS](eos-property-ado.md), the current position will simply remain at **EOS**.</span></span>

<span data-ttu-id="74d41-111">**SkipLine** 方法用于文本流（[Type](type-property-ado-stream.md) 为 **adTypeText**）。</span><span class="sxs-lookup"><span data-stu-id="74d41-111">The **SkipLine** method is used with text streams ([Type](type-property-ado-stream.md) is **adTypeText**).</span></span>

