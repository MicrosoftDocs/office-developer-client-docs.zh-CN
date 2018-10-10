---
title: Handler 属性 (RDS)
TOCTitle: Handler Property (RDS)
ms:assetid: aaf8c8c6-f95b-3cf3-b3f6-203f37464c87
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249792(v=office.15)
ms:contentKeyID: 48546962
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2a020dfa5935cfe6a0b942c5234eda2a91c40d51
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467144"
---
# <a name="handler-property-rds"></a><span data-ttu-id="2921a-102">Handler 属性 (RDS)</span><span class="sxs-lookup"><span data-stu-id="2921a-102">Handler Property (RDS)</span></span>


<span data-ttu-id="2921a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="2921a-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="2921a-104">指示扩展 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 功能的服务器端自定义程序（处理程序）的名称和该*处理程序*使用的任何参数。</span><span class="sxs-lookup"><span data-stu-id="2921a-104">Indicates the name of a server-side customization program (handler) that extends the functionality of the [RDSServer.DataFactory](datafactory-object-rdsserver.md), and any parameters used by the *handler*.</span></span>

## <a name="syntax"></a><span data-ttu-id="2921a-105">语法</span><span class="sxs-lookup"><span data-stu-id="2921a-105">Syntax</span></span>

<span data-ttu-id="2921a-106">*DataControl*。处理程序 =*字符串*</span><span class="sxs-lookup"><span data-stu-id="2921a-106">*DataControl*.Handler = *String*</span></span>

## <a name="parameters"></a><span data-ttu-id="2921a-107">参数</span><span class="sxs-lookup"><span data-stu-id="2921a-107">Parameters</span></span>

  - <span data-ttu-id="2921a-108">*DataControl*</span><span class="sxs-lookup"><span data-stu-id="2921a-108">*DataControl*</span></span>

  - <span data-ttu-id="2921a-109">一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。</span><span class="sxs-lookup"><span data-stu-id="2921a-109">An object variable that represents an [RDS.DataControl](datacontrol-object-rds.md) object.</span></span>

  - <span data-ttu-id="2921a-110">*String*</span><span class="sxs-lookup"><span data-stu-id="2921a-110">*String*</span></span>

  - <span data-ttu-id="2921a-111">一个**字符串**值，包含处理程序和任何参数，均由 （例如，"handlerName，parm1，parm2，...，parm *N"*） 的逗号分隔的名称。</span><span class="sxs-lookup"><span data-stu-id="2921a-111">A **String** value that contains the name of the handler and any parameters, all separated by commas (for example, "handlerName,parm1,parm2,...,parm *N*" ).</span></span>

## <a name="remarks"></a><span data-ttu-id="2921a-112">备注</span><span class="sxs-lookup"><span data-stu-id="2921a-112">Remarks</span></span>

<span data-ttu-id="2921a-113">此属性支持自定义，对自定义功能的支持需要将 [CursorLocation](cursorlocation-property-ado.md) 属性设置为 **adUseClient** 。</span><span class="sxs-lookup"><span data-stu-id="2921a-113">This property supports customization, a functionality that requires setting the [CursorLocation](cursorlocation-property-ado.md) property to **adUseClient**.</span></span>

<span data-ttu-id="2921a-p101">处理程序的名称及其参数（如果有）均由逗号（“,”） 分隔。如果分号（“;”）在 *String* 中的位置不固定，则会导致不可预知的行为。如果处理程序支持 **IDataFactoryHandler** 接口，则可以编写自己的处理程序。</span><span class="sxs-lookup"><span data-stu-id="2921a-p101">The name of the handler and its parameters, if any, are separated by commas (","). Unpredictable behavior will result if a semicolon (";") appears anywhere within *String*. You can write your own handler, provided it supports the **IDataFactoryHandler** interface.</span></span>

<span data-ttu-id="2921a-p102">默认处理程序的名称为 **MSDFMAP.Handler** ，其默认参数是名为 **MSDFMAP.INI** 的自定义文件。使用此属性可调用由服务器管理员创建的备用自定义文件。</span><span class="sxs-lookup"><span data-stu-id="2921a-p102">The name of the default handler is **MSDFMAP.Handler**, and its default parameter is a customization file named **MSDFMAP.INI**. Use this property to invoke alternate customization files created by your server administrator.</span></span>

<span data-ttu-id="2921a-119">设置**Handler**属性的替代方法是在[ConnectionString](connectionstring-property-ado.md)属性; 中指定处理程序和参数即"\**处理 = \*\*\* handlerName，parm1，parm2，...;*"。</span><span class="sxs-lookup"><span data-stu-id="2921a-119">The alternative to setting the **Handler** property is to specify a handler and parameters in the [ConnectionString](connectionstring-property-ado.md) property; that is, "\**Handler=\*\*\*handlerName,parm1,parm2,...;*".</span></span>

