---
title: 注册业务对象的客户端上使用 DCOM
TOCTitle: Registering business objects on the client for use with DCOM
ms:assetid: f98c419f-a8c0-b087-bb98-ab760154e99b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250269(v=office.15)
ms:contentKeyID: 48548818
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b2746ad6d0736f4415788cde477e1513d9b46146
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946802"
---
# <a name="registering-business-objects-on-the-client-for-use-with-dcom"></a><span data-ttu-id="b01b2-102">注册业务对象的客户端上使用 DCOM</span><span class="sxs-lookup"><span data-stu-id="b01b2-102">Registering business objects on the client for use with DCOM</span></span>

<span data-ttu-id="b01b2-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b01b2-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b01b2-p101">自定义业务对象时，必须确保客户端可以将业务对象的程序名 (ProgId) 映射到能通过 DCOM 使用的标识符上 (CLSID)。因此，DCOM 对象的 ProgID 必须位于客户端注册表中，并映射到服务器端业务对象的类 ID。对于其他受支持的协议（如 HTTP、HTTPS 和进程内），不需要这么做。</span><span class="sxs-lookup"><span data-stu-id="b01b2-p101">Custom business objects need to ensure that the client side can map their program name (ProgId) to an identifier (CLSID) that can be used over DCOM. For this reason, the ProgID of the DCOM object must be in the client-side registry and map to the class ID of the server-side business object. For the other supported protocols (HTTP, HTTPS, and in-process), this is not necessary.</span></span>

<span data-ttu-id="b01b2-107">例如，如果公开具有特定类 ID（如 {00112233-4455-6677-8899-00AABBCCDDEE}）的名为 MyBObj 的服务器端业务对象，请确保将以下项添加到客户端注册表中：</span><span class="sxs-lookup"><span data-stu-id="b01b2-107">For example, if you expose a server-side business object called MyBObj with a specific class ID, for instance, "{00112233-4455-6677-8899-00AABBCCDDEE}", make sure that the following entries are added to the client-side registry:</span></span>

```vb 
 
[HKEY_CLASSES_ROOT] 
\MyBObj 
 \Clsid 
 (Default) "{00112233-4455-6677-8899-00AABBCCDDEE}" 
```

