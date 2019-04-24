---
title: Handler 属性 (RDS)
TOCTitle: Handler property (RDS)
ms:assetid: aaf8c8c6-f95b-3cf3-b3f6-203f37464c87
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249792(v=office.15)
ms:contentKeyID: 48546962
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c3ad91f0a288b9908a5af5f92d7bfca3b23cdfe9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292067"
---
# <a name="handler-property-rds"></a><span data-ttu-id="ded00-102">Handler 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="ded00-102">Handler property (RDS)</span></span>

<span data-ttu-id="ded00-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ded00-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ded00-104">指示扩展 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 功能的服务器端自定义程序（处理程序）的名称和该*处理程序*使用的任何参数。</span><span class="sxs-lookup"><span data-stu-id="ded00-104">Indicates the name of a server-side customization program (handler) that extends the functionality of the [RDSServer.DataFactory](datafactory-object-rdsserver.md), and any parameters used by the *handler*.</span></span>

## <a name="syntax"></a><span data-ttu-id="ded00-105">语法</span><span class="sxs-lookup"><span data-stu-id="ded00-105">Syntax</span></span>

<span data-ttu-id="ded00-106">*rds.datacontrol*。处理程序 = *String*</span><span class="sxs-lookup"><span data-stu-id="ded00-106">*DataControl*.Handler = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="ded00-107">参数</span><span class="sxs-lookup"><span data-stu-id="ded00-107">Parameters</span></span>

|<span data-ttu-id="ded00-108">参数</span><span class="sxs-lookup"><span data-stu-id="ded00-108">Parameter</span></span>|<span data-ttu-id="ded00-109">描述</span><span class="sxs-lookup"><span data-stu-id="ded00-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="ded00-110">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="ded00-110">*DataControl*</span></span> |<span data-ttu-id="ded00-111">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="ded00-111">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>|
|<span data-ttu-id="ded00-112">*String*</span><span class="sxs-lookup"><span data-stu-id="ded00-112">*String*</span></span> |<span data-ttu-id="ded00-113">一个**字符串**值, 包含处理程序的名称和任何参数, 均由逗号分隔 (例如, "handlerName, parm1, parm2,..., parm *N*")。</span><span class="sxs-lookup"><span data-stu-id="ded00-113">A **String** value that contains the name of the handler and any parameters, all separated by commas (for example, "handlerName,parm1,parm2,...,parm *N*" ).</span></span>|

## <a name="remarks"></a><span data-ttu-id="ded00-114">注解</span><span class="sxs-lookup"><span data-stu-id="ded00-114">Remarks</span></span>

<span data-ttu-id="ded00-115">此属性支持自定义，对自定义功能的支持需要将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient**。</span><span class="sxs-lookup"><span data-stu-id="ded00-115">This property supports customization, a functionality that requires setting the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient**.</span></span>

<span data-ttu-id="ded00-p101">处理程序的名称及其参数（如果有）均由逗号（“,”） 分隔。如果分号（“;”）在 *String* 中的位置不固定，则会导致不可预知的行为。如果处理程序支持 **IDataFactoryHandler** 接口，则可以编写自己的处理程序。</span><span class="sxs-lookup"><span data-stu-id="ded00-p101">The name of the handler and its parameters, if any, are separated by commas (","). Unpredictable behavior will result if a semicolon (";") appears anywhere within *String*. You can write your own handler, provided it supports the **IDataFactoryHandler** interface.</span></span>

<span data-ttu-id="ded00-p102">默认处理程序的名称为 **MSDFMAP.Handler** ，其默认参数是名为 **MSDFMAP.INI** 的自定义文件。使用此属性可调用由服务器管理员创建的备用自定义文件。</span><span class="sxs-lookup"><span data-stu-id="ded00-p102">The name of the default handler is **MSDFMAP.Handler**, and its default parameter is a customization file named **MSDFMAP.INI**. Use this property to invoke alternate customization files created by your server administrator.</span></span>

<span data-ttu-id="ded00-121">设置**handler**属性的另一种方法是在[ConnectionString](connectionstring-property-ado.md)属性中指定处理程序和参数;即 "\**Handler = \* \* \* handlerName, parm1, parm2,...;*"。</span><span class="sxs-lookup"><span data-stu-id="ded00-121">The alternative to setting the **Handler** property is to specify a handler and parameters in the [ConnectionString](connectionstring-property-ado.md) property; that is, "\**Handler=\*\*\*handlerName,parm1,parm2,...;*".</span></span>

