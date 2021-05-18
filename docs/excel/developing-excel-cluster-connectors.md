---
title: 开发 Excel 群集连接器
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b538ae44-37d2-496b-b6e7-b0e39f6e38cb
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e1c70713586a7a143f119a2c3e9d34b982dcedba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412595"
---
# <a name="developing-excel-cluster-connectors"></a>开发 Excel 群集连接器

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Excel群集连接器提供了一种自动将 XLL 中的群集安全用户定义函数调用卸载到群集服务器的方式。 有关群集安全用户定义函数的说明，请参阅[群集保险箱函数](cluster-safe-functions.md)。 通过允许使用更多计算资源，此卸载可以提高性能。 群集连接器通常由高性能计算群集供应商开发。
  
## <a name="cluster-connectors"></a>群集连接器

群集连接器是一个 DLL，它提供定义的入口点Excel用于协调群集安全的用户定义函数调用。 它充当 Excel 和高性能计算群集之间的接口，用于会话管理、通过传递完全限定的函数名称和调用的实际参数) 来调用 (，以及通过回调机制将调用结果返回到 Excel。
  
若要创建群集连接器，请创建公开群集连接器函数 中列出的Excel [DLL。](excel-cluster-connector-functions.md)
  
## <a name="installing-a-cluster-connector"></a>安装群集连接器

若要使群集连接器在 Excel中可用，连接器的安装代码必须在安装了该连接器Excel DLL。 此外，连接器的设置代码必须在以下注册表项下添加连接器的条目：
  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\Excel\Excel Cluster Connectors\
  
为群集连接器的此键添加一个节点，该节点指定以下字符串：
  
-  `Name`- 将在群集连接器列表中显示的名称Excel。
    
-  `Filename`- DLL 的完整路径。
    

