---
title: 设置 DCOM 流封送处理格式
TOCTitle: Setting DCOM Stream Marshaling Format
ms:assetid: 5f75fc59-a9f8-6686-07f9-de292e4da787
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249346(v=office.15)
ms:contentKeyID: 48545162
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c0c05a378624f118f1bf6f070273b686a2e50a6e
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467316"
---
# <a name="setting-dcom-stream-marshaling-format"></a>设置 DCOM 流封送处理格式


**适用于**： Access 2013 |Office 2013

使用 RDS 1.5 或较早版本组件的客户端计算机与使用 RDS 2.0 或更高版本组件的服务器不兼容。如果将 DCOM 作为基础协议，则对 RDS 2.0 或更高版本的支持将使 [Recordset](recordset-object-ado.md) 对象的传输更为高效。如果客户端运行的是 RDS 1.5 或较早版本的组件，那么可以将服务器设置为采用以前的 RDS 支持（称为 RDS 1.0）或较新的 RDS 支持（称为 RDS 2.0 或更高版本）。请设置以下注册表项中的一项：

```vb 
 
[HKEY_CLASSES_ROOT] 
\CLSID 
 \[58ECEE30-E715-11CF-B0E3-00AA003F000F} 
 \ADTGOptions]"MarshalFormat"="RDS10" 
```

\-或-

```vb 
 
[HKEY_CLASSES_ROOT] 
\CLSID 
 \[58ECEE30-E715-11CF-B0E3-00AA003F000F} 
 \ADTGOptions]"MarshalFormat"="RDS20" 
```

