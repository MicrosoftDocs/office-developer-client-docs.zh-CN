---
title: Flush 方法-ActiveX 数据对象 (ADO)
TOCTitle: Flush method (ADO)
ms:assetid: c167e3b1-c133-ce45-6cee-5a1280a1568f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249941(v=office.15)
ms:contentKeyID: 48547529
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e2a55eb66c454d510d53083c495326548eda08af
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708030"
---
# <a name="flush-method-ado"></a>Flush 方法 (ADO)


**适用于**： Access 2013、 Office 2013

用于将保留在 ADO 缓冲区中的 [Stream](stream-object-ado.md) 的内容强制转移到 **Stream** 所关联的基础对象中。

## <a name="syntax"></a>语法

*流*。刷新

## <a name="remarks"></a>备注

该方法可用于将流缓冲区的内容发送到基础对象（例如，由 URL 表示的作为 **Stream** 对象的源的节点或文件）。当您希望确保已写入对 **Stream** 内容所做的所有更改时，应调用该方法。不过，使用 ADO 时，通常不需要调用 **Flush** ，因为 ADO 会在后台尽可能地持续刷新其缓冲区。对 **Stream** 内容的更改是自动进行的，且直到调用 **Flush** 时才进行缓存。

使用 **Close** 方法关闭 [Stream](close-method-ado.md) 将自动刷新 **Stream** 的内容；在马上要 **关闭** 流之前不需要显式调用 **Flush** 。

