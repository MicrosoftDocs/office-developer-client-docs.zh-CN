---
title: 在 IIS 上指定每个处理器的线程数
TOCTitle: Specifying Threads Per Processor on IIS
ms:assetid: 12889d7b-5415-8077-2ca0-1c3a96fb89ec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248898(v=office.15)
ms:contentKeyID: 48543344
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5041eb32397fc9a234d0e4a0fff622f31b56a0a5
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25603355"
---
# <a name="specifying-threads-per-processor-on-iis"></a>在 IIS 上指定每个处理器的线程数


**适用于**： Access 2013 |Office 2013

<<<<<<< 标头时使用 RDS Internet 信息服务 4.0 或更高版本，可通过操作 Web 服务器上的注册表来控制创建每个处理器的线程数。 在高通讯量或者通讯量虽小但查询较大的情况下，每处理器的线程数可能会影响性能。 用户应进行试验以获得最佳效果。
=== 时使用 RDS Internet 信息服务 4.0 或更高版本，可通过操作 web 服务器上的注册表控制创建每个处理器的线程数。 在高通讯量或者通讯量虽小但查询较大的情况下，每处理器的线程数可能会影响性能。 用户应进行试验以获得最佳效果。
>>>>>>> master

用来确定和更改此设置默认值的方法取决于 IIS 4.0 服务器的配置。

如果 IIS 服务器上装有 MDAC 2.1.2.4202.3 (GA) 或更高版本，RDS 将与 ASP 脚本使用相同的组件服务（如果您使用的是 Windows NT，则为 Microsoft Transaction Services）线程池。每处理器线程数的默认值是 10。若要更改该默认值，必须向服务器注册表中添加以下注册表项：

```vb 
 
HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\InetInfo\Parameters\MaxPoolThreads
```

其中*MaxPoolThreads*是注册表\_DWORD。 除非明确添加到注册表中未显示*MaxPoolThreads* 。 有效值的范围是从 5 到建议的最大值 20。 如果指定的注册表项的值大于*PoolThreadLimit*项 （位于同一路径下） 的值，则使用*PoolThreadLimit*值。

或者，如果在 IIS 服务器上装有 MDAC 2.1 2.1.1.3711.11 (GA) 或更低版本，则每处理器线程数的默认值为 6。若要更改该默认值，则必须向 IIS 服务器上的注册表中添加以下注册表项：

```vb 
 
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\W3SVC\Parameters\ADCThreads
```

其中*ADCThreads*是注册表\_DWORD。 除非明确添加到注册表中未显示*ADCThreads* 。 有效值的范围是从 1 到 50。 如果由注册表项指定的值大于 50，则将使用最大值 (50)。

