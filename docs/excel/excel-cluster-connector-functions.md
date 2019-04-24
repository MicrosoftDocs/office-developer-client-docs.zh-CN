---
title: Excel 群集连接器函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 65927ef9-29f7-499a-a1c1-6f672c09bb6b
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 41a5cf1ecb7c8f38f4aa5b62a493b3f45c2fe090
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311065"
---
# <a name="excel-cluster-connector-functions"></a>Excel 群集连接器函数

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 2013 群集连接器 dll 必须实现本节中所述的函数。
  
本节的参考主题中提到的返回值在 SDK 包含文件 xlcall.h 中进行定义。
  
## <a name="cluster-connector-architecture"></a>群集连接器体系结构

Excel 将调用群集连接器中的入口点, 以将用户定义的函数调用传输到高性能计算群集, 并将其用于群集会话管理。
  
## <a name="in-this-section"></a>本节内容

[CallUDF](calludf.md)
  
[CancelOutstandingRequests](canceloutstandingrequests.md)
  
[CloseSession](closesession.md)
  
[OpenSession](opensession.md)
  
[PingSession](pingsession.md)
  
[ShowOptions](showoptions.md)
  
## <a name="see-also"></a>另请参阅



[Developing Excel Cluster Connectors](developing-excel-cluster-connectors.md)
  
[群集安全函数](cluster-safe-functions.md)

