---
title: ConvertToString 方法 (RDS)
TOCTitle: ConvertToString Method (RDS)
ms:assetid: dc6381e4-98c8-badc-ad8c-87c70574a8a4
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250113(v=office.15)
ms:contentKeyID: 48548136
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fa1a4326cf318a9cbcddf8ebcdf584543ac8ebfb
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468283"
---
# <a name="converttostring-method-rds"></a><span data-ttu-id="ba712-102">ConvertToString 方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="ba712-102">ConvertToString Method (RDS)</span></span>


<span data-ttu-id="ba712-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ba712-103">**Applies to**: Access 2013 | Office 2013</span></span> 

<span data-ttu-id="ba712-104">将 [Recordset](recordset-object-ado.md) 转换为代表记录集数据的 MIME 字符串。</span><span class="sxs-lookup"><span data-stu-id="ba712-104">Converts a [Recordset](recordset-object-ado.md) to a MIME string that represents the recordset data.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba712-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba712-105">Syntax</span></span>

<span data-ttu-id="ba712-106">*DataFactory*。ConvertToString (*Recordset*)</span><span class="sxs-lookup"><span data-stu-id="ba712-106">*DataFactory*.ConvertToString(*Recordset*)</span></span>

## <a name="parameters"></a><span data-ttu-id="ba712-107">参数</span><span class="sxs-lookup"><span data-stu-id="ba712-107">Parameters</span></span>

  - <span data-ttu-id="ba712-108">*DataFactory*</span><span class="sxs-lookup"><span data-stu-id="ba712-108">*DataFactory*</span></span>

  - <span data-ttu-id="ba712-109">一个代表 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="ba712-109">An object variable that represents an [RDSServer.DataFactory](datafactory-object-rdsserver.md) object.</span></span>

  - <span data-ttu-id="ba712-110">*Recordset*</span><span class="sxs-lookup"><span data-stu-id="ba712-110">*Recordset*</span></span>

  - <span data-ttu-id="ba712-111">一个代表 **Recordset** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="ba712-111">An object variable that represents a **Recordset** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba712-112">说明</span><span class="sxs-lookup"><span data-stu-id="ba712-112">Remarks</span></span>

<span data-ttu-id="ba712-113">利用 .asp 文件，使用 **ConvertToString** 将 **Recordset** 嵌入到服务器上生成的 HTML 页，以将该记录集传输到客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="ba712-113">With .asp files, use **ConvertToString** to embed the **Recordset** in an HTML page generated on the server to transport it to a client computer.</span></span>

<span data-ttu-id="ba712-114">**ConvertToString** 首先将 **Recordset** 加载到"游标服务"表中，然后生成 MIME 格式的流。</span><span class="sxs-lookup"><span data-stu-id="ba712-114">**ConvertToString** first loads the **Recordset** into the Cursor Service tables, and then generates a stream in MIME format.</span></span>

<span data-ttu-id="ba712-p101">在客户端，远程数据服务可以将 MIME 字符串转换回功能完整的 **Recordset** 。这种功能可以很好地处理少于 400 行、每行宽度不超过 1024 字节的数据。但在通过 HTTP 在以流方式传输 BLOB 数据和较大的结果集时，不应使用该功能。在字符串上不会执行在线压缩，因此与由远程数据服务定义和部署为其自己的传输协议格式的在线优化的表图格式相比，很大的数据集在通过 HTTP 传输时将花费相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="ba712-p101">On the client, Remote Data Service can convert the MIME string back into a fully functioning **Recordset**. It works well for handling fewer than 400 rows of data with no more than 1024 bytes width per row. You shouldn't use it for streaming BLOB data and large result sets over HTTP. No wire compression is performed on the string, so very large data sets will take considerable time to transport over HTTP when compared to the wire-optimized tablegram format defined and deployed by Remote Data Service as its native transport protocol format.</span></span>


> [!NOTE]
> <P><span data-ttu-id="ba712-p102">[!注释] 如果要使用 Active Server 页将生成的 MIME 字符串嵌入客户端 HTML 页，请注意低于 2.0 版的 VBScript 会将字符串大小限制为 32K。如果超过此限制，将返回一个错误。通过 .asp 文件使用 MIME 嵌入功能时，请保持相对较小的查询范围。若要修复此问题，请从 <A href="https://www.microsoft.com/downloads/en/default.aspx">Microsoft 下载中心</A>下载最新版本的 VBScript。</span><span class="sxs-lookup"><span data-stu-id="ba712-p102">If you are using Active Server Pages to embed the resulting MIME string in a client HTML page, be aware that versions of VBScript earlier than version 2.0 limit the string's size to 32K. If this limit is exceeded, an error is returned. Keep the query scope relatively small when using MIME embedding via .asp files. To fix this, download the latest version of VBScript from the <A href="https://www.microsoft.com/downloads/en/default.aspx">Microsoft Download Center</A>.</span></span></P>


