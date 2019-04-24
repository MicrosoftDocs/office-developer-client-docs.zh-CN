---
title: 开发 Excel 群集连接器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b538ae44-37d2-496b-b6e7-b0e39f6e38cb
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e1c70713586a7a143f119a2c3e9d34b982dcedba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310953"
---
# <a name="developing-excel-cluster-connectors"></a>开发 Excel 群集连接器

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Excel 群集连接器提供了一种方法, 用于将 XLL 中的群集安全用户定义的函数调用自动卸载到群集服务器。 有关群集安全用户定义的函数的说明, 请参阅[群集安全函数](cluster-safe-functions.md)。 此卸载可以通过启用更多的计算资源来提高性能。 群集连接器通常由高性能计算群集供应商开发。
  
## <a name="cluster-connectors"></a>群集连接器

群集连接器是提供定义的入口点的 DLL, Excel 使用这些入口点来协调群集安全用户定义的函数调用。 它充当 excel 和高性能计算群集之间的接口, 用于实现函数调用 (通过传递完全限定的函数名称和调用的实际参数), 以及将呼叫结果返回到 Excel 的过程回调机制。
  
若要创建群集连接器, 请创建一个 DLL, 用于公开在[Excel 群集连接器函数](excel-cluster-connector-functions.md)中列出的入口点。
  
## <a name="installing-a-cluster-connector"></a>安装群集连接器

若要使群集连接器在 excel 中可用, 连接器的安装代码必须在安装了 excel 的计算机上安装连接器的 DLL。 此外, 连接器的安装程序代码必须在以下注册表项下添加连接器的条目:
  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel 群集连接器 \
  
将节点添加到指定以下字符串的群集连接器的此项中:
  
-  `Name`—将显示在 Excel 中的群集连接器列表中的名称。
    
-  `Filename`— DLL 的完整路径。
    

