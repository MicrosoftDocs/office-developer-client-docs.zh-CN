---
title: 设置 DCOM 流封送格式
TOCTitle: Setting DCOM stream marshaling format
ms:assetid: 5f75fc59-a9f8-6686-07f9-de292e4da787
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249346(v=office.15)
ms:contentKeyID: 48545162
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 09463552faff9c4b74b73379385ab8ba55b4f62c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308664"
---
# <a name="setting-dcom-stream-marshaling-format"></a><span data-ttu-id="7e83c-102">设置 DCOM 流封送格式</span><span class="sxs-lookup"><span data-stu-id="7e83c-102">Setting DCOM stream marshaling format</span></span>


<span data-ttu-id="7e83c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7e83c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7e83c-p101">使用 RDS 1.5 或较早版本组件的客户端计算机与使用 RDS 2.0 或更高版本组件的服务器不兼容。如果将 DCOM 作为基础协议，则对 RDS 2.0 或更高版本的支持将使 [Recordset](recordset-object-ado.md) 对象的传输更为高效。如果客户端运行的是 RDS 1.5 或较早版本的组件，那么可以将服务器设置为采用以前的 RDS 支持（称为 RDS 1.0）或较新的 RDS 支持（称为 RDS 2.0 或更高版本）。请设置以下注册表项中的一项：</span><span class="sxs-lookup"><span data-stu-id="7e83c-p101">A client computer using components from RDS 1.5 or earlier is not compatible with a server using components from RDS 2.0 or later. When using DCOM as the underlying protocol, the support for RDS 2.0 or later is more efficient in transporting [Recordset](recordset-object-ado.md) objects. If your client is running components from RDS 1.5 or earlier, you can set your server to work with the previous RDS support (called RDS 1.0) or the newer RDS support (called RDS 2.0 or later). Set either of the following registry entries:</span></span>

```vb 
 
[HKEY_CLASSES_ROOT] 
\CLSID 
 \[58ECEE30-E715-11CF-B0E3-00AA003F000F} 
 \ADTGOptions]"MarshalFormat"="RDS10" 
```

<span data-ttu-id="7e83c-108">\-和</span><span class="sxs-lookup"><span data-stu-id="7e83c-108">\-or-</span></span>

```vb 
 
[HKEY_CLASSES_ROOT] 
\CLSID 
 \[58ECEE30-E715-11CF-B0E3-00AA003F000F} 
 \ADTGOptions]"MarshalFormat"="RDS20" 
```

