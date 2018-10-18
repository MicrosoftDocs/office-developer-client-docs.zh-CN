---
title: CreateObject 方法 (RDS)
TOCTitle: CreateObject Method (RDS)
ms:assetid: 130debe5-31cf-4ab0-5f78-9adaec7d7126
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248905(v=office.15)
ms:contentKeyID: 48543360
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d2ff2381626e8cf81aa95ee9d49f9396bd4b0316
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25602718"
---
# <a name="createobject-method-rds"></a>CreateObject 方法 (RDS)


**适用于**： Access 2013 |Office 2013


用于创建目标业务对象的代理，并返回指向该代理的指针。代理打包数据并将其封送到服务器端存根，用于与业务对象进行通信，以便通过 Internet 发送请求和数据。对于进程内组件对象，不使用代理，而仅提供指向对象的指针。

## <a name="syntax"></a>语法

远程数据服务支持以下协议：HTTP、HTTPS（基于安全套接字层的 HTTP）、DCOM 和进程内。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>协议</p></th>
<th><p>语法</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP</p></td>
<td><p>将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; <em>https://awebsrvr</em> &quot;)</p></td>
</tr>
<tr class="even">
<td><p>HTTPS</p></td>
<td><p>将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; <em>https://awebsrvr</em> &quot;)</p></td>
</tr>
<tr class="odd">
<td><p>DCOM</p></td>
<td><p>将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; <em>computername</em>&quot;)</p></td>
</tr>
<tr class="even">
<td><p>In-process</p></td>
<td><p>将<em>对象</em>设置 = <em>DataSpace</em>。CreateObject (&quot;<em>ProgId</em>&quot;， &quot; &quot;)</p></td>
</tr>
</tbody>
</table>


## <a name="parameters"></a>参数

  - *Object*

  - 一个对象变量，其值为 *ProgID* 中指定类型的对象。

  - *DataSpace*

  - 对象变量，代表用于创建新对象实例的 [RDS.DataSpace](dataspace-object-rds.md) 对象。

  - *ProgID*

  - 一个包含程序标识符的 **String** 值，指定用于实现应用程序的业务规则的服务器端业务对象。

  - *awebsrvr*或*computername*

<<<<<<< 标头
  - **字符串型** 值，代表标识在其中创建服务器业务对象实例的 Internet 信息服务 (IIS) Web 服务器的 URL。

## <a name="remarks"></a>说明

<a name="the-http-protocol-is-the-standard-web-protocol-https-is-a-secure-web-protocol-use-the-dcom-protocol-when-running-a-local-area-network-without-http-the-in-process-protocol-is-a-local-dynamic-link-library-dll-it-does-not-use-a-network"></a>*HTTP 协议*是标准的 Web 协议;*HTTPS*是安全的 Web 协议。 运行没有 HTTP 的本地网络时，请使用*DCOM 协议*。 *进程内*协议是本地的动态链接库 (DLL);它不使用网络。
=======
  - 一个**字符串**值，代表标识在其中创建服务器业务对象的实例的 Internet 信息服务 (IIS) web 服务器的 URL。

## <a name="remarks"></a>说明

*HTTP 协议*是标准的 web 协议;*HTTPS*是安全的 web 协议。 运行没有 HTTP 的本地网络时，请使用*DCOM 协议*。 *进程内*协议是本地的动态链接库 (DLL);它不使用网络。
>>>>>>> master

