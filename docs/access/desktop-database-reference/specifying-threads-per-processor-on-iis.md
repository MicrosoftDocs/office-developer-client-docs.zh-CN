---
title: 在 IIS 上指定每个处理器的线程数
TOCTitle: Specifying threads per processor on IIS
ms:assetid: 12889d7b-5415-8077-2ca0-1c3a96fb89ec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248898(v=office.15)
ms:contentKeyID: 48543344
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 57e4b6228588af7f0d58caf53d3e093e824c7854
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308587"
---
# <a name="specifying-threads-per-processor-on-iis"></a>在 IIS 上指定每个处理器的线程数


**适用于**：Access 2013、Office 2013

在将 RDS 与 Internet 信息服务4.0 或更高版本一起使用时, 可以通过操作 web 服务器上的注册表来控制为每个处理器创建的线程数。 在高通讯量或者通讯量虽小但查询较大的情况下，每处理器的线程数可能会影响性能。 用户应进行试验以获得最佳效果。

用来确定和更改此设置默认值的方法取决于 IIS 4.0 服务器的配置。

如果 IIS 服务器上装有 MDAC 2.1.2.4202.3 (GA) 或更高版本，RDS 将与 ASP 脚本使用相同的组件服务（如果您使用的是 Windows NT，则为 Microsoft Transaction Services）线程池。每处理器线程数的默认值是 10。若要更改该默认值，必须向服务器注册表中添加以下注册表项：

```vb 
 
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\MaxPoolThreads
```

其中, *MaxPoolThreads*是 REG\_DWORD。 除非特意添加，否则 *MaxPoolThreads* 不出现在注册表中。 有效值的范围是从 5 到建议的最大值 20。 如果注册表项指定的值大于 *PoolThreadLimit* 项（位于同一路径下）的值，则使用 *PoolThreadLimit* 值。

或者，如果在 IIS 服务器上装有 MDAC 2.1 2.1.1.3711.11 (GA) 或更低版本，则每处理器线程数的默认值为 6。若要更改该默认值，则必须向 IIS 服务器上的注册表中添加以下注册表项：

```vb 
 
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W3SVC\Parameters\ADCThreads
```

其中, *ADCThreads*是 REG\_DWORD。 除非特意添加，否则 *ADCThreads* 将不出现在注册表中。 有效值的范围是从 1 到 50。 如果由注册表项指定的值大于 50，则将使用最大值 (50)。

