---
title: 开发 Excel 群集连接器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b538ae44-37d2-496b-b6e7-b0e39f6e38cb
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 8c9a166ac06685c0a450e1e0bd60b2fbef67d336
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773632"
---
# <a name="developing-excel-cluster-connectors"></a>开发 Excel 群集连接器

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Excel 群集连接器的自动卸载用户定义的群集安全函数调用中 XLL 群集服务器提供一种方法。 群集安全用户定义函数的说明，请参阅[群集安全函数](cluster-safe-functions.md)。 此卸载可以通过启用详细计算的资源用于提高性能。 群集连接器通常是由高性能计算群集供应商开发。
  
## <a name="cluster-connectors"></a>群集连接器

群集连接器是 DLL 提供定义的入口点，Excel 用来协调群集安全用户定义函数调用。 会话管理，使函数调用 （通过将传递的完全限定的函数名称和调用的实际参数），以及呼叫结果返回到 Excel 通过充当 Excel 和高性能计算群集，之间的接口回调机制。
  
若要创建群集连接器，请创建 DLL 公开[Excel 群集连接器函数](excel-cluster-connector-functions.md)中列出的入口点。
  
## <a name="installing-a-cluster-connector"></a>安装群集连接器

使群集连接器在 Excel 中可用，连接器的安装程序代码必须安装 Excel 的计算机上安装的 DLL 的连接器。 此外，连接器的安装程序代码必须添加以下注册表项下连接器条目：
  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel 群集 Connectors\
  
将节点添加到此密钥的群集连接器，指定以下字符串：
  
-  `Name`— 将出现在 Excel 中的群集连接器的列表的名称。
    
-  `Filename`— DLL 的完整路径。
    

