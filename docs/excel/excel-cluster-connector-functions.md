---
title: Excel群集连接器功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 65927ef9-29f7-499a-a1c1-6f672c09bb6b
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 41a5cf1ecb7c8f38f4aa5b62a493b3f45c2fe090
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408584"
---
# <a name="excel-cluster-connector-functions"></a>Excel群集连接器功能

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 2013群集连接器 DLL 必须实现本节中所述的功能。
  
本节参考主题中提到的返回值在 SDK include 文件 xlcall.h 中定义。
  
## <a name="cluster-connector-architecture"></a>群集连接器体系结构

Excel调用群集连接器中的入口点，以将用户定义函数调用转移到高性能计算群集以及用于群集会话管理。
  
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

