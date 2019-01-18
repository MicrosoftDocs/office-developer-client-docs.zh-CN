---
title: SkipLine 方法 (ADO)
TOCTitle: SkipLine method (ADO)
ms:assetid: 419c24c3-6b84-eed0-5884-f2dcd485dc3d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249187(v=office.15)
ms:contentKeyID: 48544456
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5e49b8379f078ad698a4a0040de0eb2e4429fd34
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718775"
---
# <a name="skipline-method-ado"></a>SkipLine 方法 (ADO)


**适用于**： Access 2013、 Office 2013

用于在读取文本流时跳过一整行。

## <a name="syntax"></a>语法

*流*。SkipLine

## <a name="remarks"></a>备注

跳过下一个行分隔符（含）之前的所有字符。默认情况下，[LineSeparator](lineseparator-property-ado.md) 为 **adCRLF** 。如果试图跳过 [EOS](eos-property-ado.md)，则当前位置将只保持在 **EOS** 。

**SkipLine** 方法用于文本流（[Type](type-property-ado-stream.md) 为 **adTypeText**）。

