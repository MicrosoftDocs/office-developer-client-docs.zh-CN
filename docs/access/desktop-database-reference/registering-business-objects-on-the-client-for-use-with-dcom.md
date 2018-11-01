---
title: 在客户端上注册业务对象以用于 DCOM
TOCTitle: Registering Business Objects on the Client for Use with DCOM
ms:assetid: f98c419f-a8c0-b087-bb98-ab760154e99b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250269(v=office.15)
ms:contentKeyID: 48548818
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a9b106fa88df8205595312aaebdabf82cf12d57c
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887808"
---
# <a name="registering-business-objects-on-the-client-for-use-with-dcom"></a>在客户端上注册业务对象以用于 DCOM


**适用于**： Access 2013、 Office 2013

自定义业务对象时，必须确保客户端可以将业务对象的程序名 (ProgId) 映射到能通过 DCOM 使用的标识符上 (CLSID)。因此，DCOM 对象的 ProgID 必须位于客户端注册表中，并映射到服务器端业务对象的类 ID。对于其他受支持的协议（如 HTTP、HTTPS 和进程内），不需要这么做。

例如，如果公开具有特定类 ID（如 {00112233-4455-6677-8899-00AABBCCDDEE}）的名为 MyBObj 的服务器端业务对象，请确保将以下项添加到客户端注册表中：

```vb 
 
[HKEY_CLASSES_ROOT] 
\MyBObj 
 \Clsid 
 (Default) "{00112233-4455-6677-8899-00AABBCCDDEE}" 
```

