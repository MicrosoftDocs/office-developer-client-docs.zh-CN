---
title: URL 属性 (RDS-访问桌面数据库引用)
TOCTitle: URL property (RDS)
ms:assetid: 722765dc-f89c-0131-73b1-69c56a795546
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249457(v=office.15)
ms:contentKeyID: 48545603
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aafc8cc10410cafed21e38ad7fec269c391c1fa2
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702388"
---
# <a name="url-property-rds"></a><span data-ttu-id="04fe1-102">URL 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="04fe1-102">URL property (RDS)</span></span>

<span data-ttu-id="04fe1-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="04fe1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="04fe1-104">指示包含相对或绝对 URL 的字符串。</span><span class="sxs-lookup"><span data-stu-id="04fe1-104">Indicates a string that contains a relative or absolute URL.</span></span>

<span data-ttu-id="04fe1-105">可在设计时在 **DataControl** 对象的 OBJECT 标记中设置 [URL](datacontrol-object-rds.md) 属性，或者在运行时在脚本代码中设置此属性。</span><span class="sxs-lookup"><span data-stu-id="04fe1-105">You can set the **URL** property at design time in the [DataControl](datacontrol-object-rds.md) object's OBJECT tag, or at run time in scripting code.</span></span>

## <a name="syntax"></a><span data-ttu-id="04fe1-106">语法</span><span class="sxs-lookup"><span data-stu-id="04fe1-106">Syntax</span></span>

<span data-ttu-id="04fe1-107">设计时：\<参数名称 = 值"URL"="服务器"\></span><span class="sxs-lookup"><span data-stu-id="04fe1-107">Design time: \<PARAM NAME="URL" VALUE="Server"\></span></span>

<span data-ttu-id="04fe1-108">运行时间： DataControl.URL="Server"</span><span class="sxs-lookup"><span data-stu-id="04fe1-108">Run time: DataControl.URL="Server"</span></span>

## <a name="parameters"></a><span data-ttu-id="04fe1-109">Parameters</span><span class="sxs-lookup"><span data-stu-id="04fe1-109">Parameters</span></span>

|<span data-ttu-id="04fe1-110">参数</span><span class="sxs-lookup"><span data-stu-id="04fe1-110">Parameter</span></span>|<span data-ttu-id="04fe1-111">说明</span><span class="sxs-lookup"><span data-stu-id="04fe1-111">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="04fe1-112">*Server*</span><span class="sxs-lookup"><span data-stu-id="04fe1-112">*Server*</span></span> |<span data-ttu-id="04fe1-113">包含有效 URL 的 **String** 值。</span><span class="sxs-lookup"><span data-stu-id="04fe1-113">A **String** value that contains a valid URL.</span></span>|
|<span data-ttu-id="04fe1-114">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="04fe1-114">*DataControl*</span></span> |<span data-ttu-id="04fe1-115">一个代表 **DataControl** 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="04fe1-115">An object variable that represents a **DataControl** object.</span></span>|

## <a name="remarks"></a><span data-ttu-id="04fe1-116">备注</span><span class="sxs-lookup"><span data-stu-id="04fe1-116">Remarks</span></span>

<span data-ttu-id="04fe1-p101">通常，URL 标识 Active Server Page (.asp) 文件，该文件可产生并返回 [Recordset](recordset-object-ado.md)。因此，用户可以获取 **Recordset** ，而不必调用服务器端 [DataFactory](datafactory-object-rdsserver.md) 对象或设计自定义业务对象。</span><span class="sxs-lookup"><span data-stu-id="04fe1-p101">Typically, the URL identifies an Active Server Page (.asp) file that can produce and return a [Recordset](recordset-object-ado.md). Therefore, the user can obtain a **Recordset** without having to invoke the server-side [DataFactory](datafactory-object-rdsserver.md) object, or program a custom business object.</span></span>

<span data-ttu-id="04fe1-119">如果设置了 **URL** 属性，则 [SubmitChanges](submitchanges-method-rds.md) 将更改提交到 URL 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="04fe1-119">If the **URL** property has been set, [SubmitChanges](submitchanges-method-rds.md) will submit changes to the location specified by the URL.</span></span>

