```bash
CREATE DEFAULT
this is a SSO login
workspace name: {}workspaceID1: {}670773d4cd32ef7400f0c6c3
WorkspaceID2: {}670773d4cd32ef7400f0c6c3
[2024-10-10 06:29:46,969] requestId= userEmail= traceId= spanId= - [a45aaf87-12]  500 Server Error for HTTP GET "/login/oauth2/code/sapcdc?code=st2.s.AtLtcvezWw.Mc1KFX32DaOCMp_GVnYonhJinMEyo_0N2Xcy4xEUvSOvfSAwWhrY8w-XPjcaR4xCAtcIdEiUIJ17unPHUkQge3U-cCo1h4Sfq436Jpf5CClD0fGm8I0V29vCNyQXRtAe.F1iIVkWA3A4hWpDmFe9tFHWtIOSjDXHuwN7hB6aavpz2tUu05_BkYyW38mzEYZ6O2H5wW7TMp5y9sWxf-TtMww.sc3&state=rw8AcJ-QKVh34o_JZDqK2W2vKRiWMHLSi0lNrCWziY4%40origin-%2fapplications"
com.appsmith.server.exceptions.AppsmithException: Unable to find workspace 670773d4cd32ef7400f0c6c3
	at com.appsmith.server.services.ce.ApplicationPageServiceCEImpl.lambda$setApplicationPolicies$23(ApplicationPageServiceCEImpl.java:498)
	Suppressed: reactor.core.publisher.FluxOnAssembly$OnAssemblyException: 
Error has been observed at the following site(s):
	*__checkpoint ⇢ OAuth2LoginAuthenticationWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ AuthenticationWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ ConditionalFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ OAuth2AuthorizationRequestRedirectWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ AuthenticationWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ ReactorContextWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ CSRFFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ HttpHeaderWriterWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ SecurityConfig$$Lambda$1779/0x00007ff0bcb6bac0 [DefaultWebFilterChain]
	*__checkpoint ⇢ ServerWebExchangeReactorContextWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ org.springframework.security.web.server.WebFilterChainProxy [DefaultWebFilterChain]
	*__checkpoint ⇢ org.springframework.web.filter.reactive.ServerHttpObservationFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ io.sentry.spring.jakarta.webflux.SentryWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ com.appsmith.server.configurations.MicrometerTraceHeaderWebFilter [DefaultWebFilterChain]
	*__checkpoint ⇢ HTTP GET "/login/oauth2/code/sapcdc?code=st2.s.AtLtcvezWw.Mc1KFX32DaOCMp_GVnYonhJinMEyo_0N2Xcy4xEUvSOvfSAwWhrY8w-XPjcaR4xCAtcIdEiUIJ17unPHUkQge3U-cCo1h4Sfq436Jpf5CClD0fGm8I0V29vCNyQXRtAe.F1iIVkWA3A4hWpDmFe9tFHWtIOSjDXHuwN7hB6aavpz2tUu05_BkYyW38mzEYZ6O2H5wW7TMp5y9sWxf-TtMww.sc3&state=rw8AcJ-QKVh34o_JZDqK2W2vKRiWMHLSi0lNrCWziY4%40origin-%2fapplications" [ExceptionHandlingWebHandler]
Original Stack Trace:
		at com.appsmith.server.services.ce.ApplicationPageServiceCEImpl.lambda$setApplicationPolicies$23(ApplicationPageServiceCEImpl.java:498)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onNext(MonoFlatMap.java:132)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.Operators$MonoSubscriber.complete(Operators.java:1839)
		at reactor.core.publisher.MonoCacheTime$CoordinatorSubscriber.signalCached(MonoCacheTime.java:337)
		at reactor.core.publisher.MonoCacheTime$CoordinatorSubscriber.onNext(MonoCacheTime.java:354)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.onNext(FluxMapFuseable.java:129)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onNext(FluxHide.java:137)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.onNext(FluxMapFuseable.java:129)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onNext(FluxHide.java:137)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.secondComplete(MonoFlatMap.java:245)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onNext(MonoFlatMap.java:305)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.Operators$ScalarSubscription.request(Operators.java:2545)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onSubscribe(MonoFlatMap.java:291)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.MonoJust.subscribe(MonoJust.java:55)
		at reactor.core.publisher.InternalMonoOperator.subscribe(InternalMonoOperator.java:64)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onNext(MonoFlatMap.java:165)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxFilter$FilterSubscriber.onNext(FluxFilter.java:113)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxMap$MapSubscriber.onNext(FluxMap.java:122)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.Operators$ScalarSubscription.request(Operators.java:2545)
		at reactor.core.publisher.FluxMap$MapSubscriber.request(FluxMap.java:164)
		at reactor.core.publisher.FluxFilter$FilterSubscriber.request(FluxFilter.java:186)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.request(MonoFlatMap.java:194)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.request(FluxHide.java:152)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.request(FluxMapFuseable.java:171)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.request(FluxHide.java:152)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.request(FluxMapFuseable.java:171)
		at reactor.core.publisher.MonoCacheTime$CoordinatorSubscriber.onSubscribe(MonoCacheTime.java:293)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.onSubscribe(FluxMapFuseable.java:96)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onSubscribe(FluxHide.java:122)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.onSubscribe(FluxMapFuseable.java:96)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onSubscribe(FluxHide.java:122)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onSubscribe(MonoFlatMap.java:117)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.FluxFilter$FilterSubscriber.onSubscribe(FluxFilter.java:85)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.FluxMap$MapSubscriber.onSubscribe(FluxMap.java:92)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.MonoJust.subscribe(MonoJust.java:55)
		at reactor.core.publisher.InternalMonoOperator.subscribe(InternalMonoOperator.java:64)
		at reactor.core.publisher.MonoDeferContextual.subscribe(MonoDeferContextual.java:55)
		at reactor.core.publisher.InternalMonoOperator.subscribe(InternalMonoOperator.java:64)
		at reactor.core.publisher.MonoCacheTime.subscribeOrReturn(MonoCacheTime.java:143)
		at reactor.core.publisher.InternalMonoOperator.subscribe(InternalMonoOperator.java:57)
		at reactor.core.publisher.MonoZip$ZipCoordinator.request(MonoZip.java:216)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.request(MonoFlatMap.java:194)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.request(FluxHide.java:152)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.request(MonoFlatMap.java:194)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onSubscribe(MonoFlatMap.java:291)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onSubscribe(MonoFlatMap.java:117)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onSubscribe(FluxHide.java:122)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onSubscribe(MonoFlatMap.java:117)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.MonoZip.subscribe(MonoZip.java:125)
		at reactor.core.publisher.InternalMonoOperator.subscribe(InternalMonoOperator.java:64)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onNext(MonoFlatMap.java:165)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onNext(FluxHide.java:137)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.secondComplete(MonoFlatMap.java:245)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onNext(MonoFlatMap.java:305)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxMapFuseable$MapFuseableSubscriber.onNext(FluxMapFuseable.java:129)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onNext(FluxHide.java:137)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.secondComplete(MonoFlatMap.java:245)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onNext(MonoFlatMap.java:305)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoNext$NextSubscriber.onNext(MonoNext.java:82)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxUsingWhen$UsingWhenSubscriber.onNext(FluxUsingWhen.java:345)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoFlatMapMany$FlatMapManyInner.onNext(MonoFlatMapMany.java:250)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.secondComplete(MonoFlatMap.java:245)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onNext(MonoFlatMap.java:305)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.Operators$ScalarSubscription.request(Operators.java:2545)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onSubscribe(MonoFlatMap.java:291)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onSubscribe(MDCConfig.java:53)
		at reactor.core.publisher.MonoJust.subscribe(MonoJust.java:55)
		at reactor.core.publisher.InternalMonoOperator.subscribe(InternalMonoOperator.java:64)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.onNext(MonoFlatMap.java:165)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onNext(FluxHide.java:137)
		at reactor.core.publisher.Operators$BaseFluxToMonoOperator.completePossiblyEmpty(Operators.java:2071)
		at reactor.core.publisher.MonoCollectList$MonoCollectListSubscriber.onComplete(MonoCollectList.java:118)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onComplete(MDCConfig.java:69)
		at reactor.core.publisher.Operators$MultiSubscriptionSubscriber.onComplete(Operators.java:2205)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onComplete(MDCConfig.java:69)
		at reactor.core.publisher.MonoFlatMapMany$FlatMapManyInner.onComplete(MonoFlatMapMany.java:260)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onComplete(MDCConfig.java:69)
		at reactor.core.publisher.FluxConcatMapNoPrefetch$FluxConcatMapNoPrefetchSubscriber.onComplete(FluxConcatMapNoPrefetch.java:240)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onComplete(MDCConfig.java:69)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onComplete(MDCConfig.java:69)
		at reactor.core.publisher.FluxCreate$BaseSink.complete(FluxCreate.java:460)
		at reactor.core.publisher.FluxCreate$BufferAsyncSink.drain(FluxCreate.java:805)
		at reactor.core.publisher.FluxCreate$BufferAsyncSink.complete(FluxCreate.java:753)
		at reactor.core.publisher.FluxCreate$SerializedFluxSink.drainLoop(FluxCreate.java:247)
		at reactor.core.publisher.FluxCreate$SerializedFluxSink.drain(FluxCreate.java:213)
		at reactor.core.publisher.FluxCreate$SerializedFluxSink.complete(FluxCreate.java:204)
		at com.mongodb.reactivestreams.client.internal.BatchCursorFlux.lambda$recurseCursor$4(BatchCursorFlux.java:102)
		at reactor.core.publisher.MonoPeekTerminal$MonoTerminalPeekSubscriber.onNext(MonoPeekTerminal.java:171)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxHide$SuppressFuseableSubscriber.onNext(FluxHide.java:137)
		at reactor.core.publisher.MonoPeekTerminal$MonoTerminalPeekSubscriber.onNext(MonoPeekTerminal.java:180)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxPeek$PeekSubscriber.onNext(FluxPeek.java:200)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoCreate$DefaultMonoSink.success(MonoCreate.java:172)
		at com.mongodb.reactivestreams.client.internal.MongoOperationPublisher.lambda$sinkToCallback$31(MongoOperationPublisher.java:577)
		at com.mongodb.internal.operation.AsyncQueryBatchCursor.next(AsyncQueryBatchCursor.java:173)
		at com.mongodb.reactivestreams.client.internal.BatchCursor.lambda$next$0(BatchCursor.java:38)
		at reactor.core.publisher.MonoCreate.subscribe(MonoCreate.java:58)
		at reactor.core.publisher.Mono.subscribe(Mono.java:4495)
		at reactor.core.publisher.Mono.subscribeWith(Mono.java:4561)
		at reactor.core.publisher.Mono.subscribe(Mono.java:4323)
		at com.mongodb.reactivestreams.client.internal.BatchCursorFlux.recurseCursor(BatchCursorFlux.java:108)
		at com.mongodb.reactivestreams.client.internal.BatchCursorFlux.lambda$subscribe$0(BatchCursorFlux.java:60)
		at reactor.core.publisher.LambdaMonoSubscriber.onNext(LambdaMonoSubscriber.java:171)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.FluxMap$MapSubscriber.onNext(FluxMap.java:122)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoNext$NextSubscriber.onNext(MonoNext.java:82)
		at reactor.core.publisher.MonoNext$NextSubscriber.onNext(MonoNext.java:82)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoFlatMap$FlatMapMain.secondComplete(MonoFlatMap.java:245)
		at reactor.core.publisher.MonoFlatMap$FlatMapInner.onNext(MonoFlatMap.java:305)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoPeekTerminal$MonoTerminalPeekSubscriber.onNext(MonoPeekTerminal.java:180)
		at com.appsmith.server.configurations.MDCConfig$MdcContextLifter.onNext(MDCConfig.java:59)
		at reactor.core.publisher.MonoCreate$DefaultMonoSink.success(MonoCreate.java:172)
		at com.mongodb.reactivestreams.client.internal.MongoOperationPublisher.lambda$sinkToCallback$31(MongoOperationPublisher.java:577)
		at com.mongodb.reactivestreams.client.internal.OperationExecutorImpl.lambda$execute$2(OperationExecutorImpl.java:94)
		at com.mongodb.internal.async.ErrorHandlingResultCallback.onResult(ErrorHandlingResultCallback.java:46)
		at com.mongodb.internal.async.function.AsyncCallbackSupplier.lambda$whenComplete$1(AsyncCallbackSupplier.java:97)
		at com.mongodb.internal.async.function.RetryingAsyncCallbackSupplier$RetryingCallback.onResult(RetryingAsyncCallbackSupplier.java:116)
		at com.mongodb.internal.async.ErrorHandlingResultCallback.onResult(ErrorHandlingResultCallback.java:46)
		at com.mongodb.internal.async.function.AsyncCallbackSupplier.lambda$whenComplete$1(AsyncCallbackSupplier.java:97)
		at com.mongodb.internal.async.ErrorHandlingResultCallback.onResult(ErrorHandlingResultCallback.java:46)
		at com.mongodb.internal.async.function.AsyncCallbackSupplier.lambda$whenComplete$1(AsyncCallbackSupplier.java:97)
		at com.mongodb.internal.operation.FindOperation$1.onResult(FindOperation.java:379)
		at com.mongodb.internal.operation.CommandOperationHelper.lambda$transformingReadCallback$10(CommandOperationHelper.java:332)
		at com.mongodb.internal.async.ErrorHandlingResultCallback.onResult(ErrorHandlingResultCallback.java:46)
		at com.mongodb.internal.connection.DefaultServer$DefaultServerProtocolExecutor$1.onResult(DefaultServer.java:242)
		at com.mongodb.internal.async.ErrorHandlingResultCallback.onResult(ErrorHandlingResultCallback.java:46)
		at com.mongodb.internal.connection.CommandProtocolImpl$1.onResult(CommandProtocolImpl.java:84)
		at com.mongodb.internal.connection.DefaultConnectionPool$PooledConnection$1.onResult(DefaultConnectionPool.java:683)
		at com.mongodb.internal.connection.UsageTrackingInternalConnection$2.onResult(UsageTrackingInternalConnection.java:159)
		at com.mongodb.internal.async.ErrorHandlingResultCallback.onResult(ErrorHandlingResultCallback.java:46)
		at com.mongodb.internal.connection.InternalStreamConnection$2$1.onResult(InternalStreamConnection.java:524)
		at com.mongodb.internal.connection.InternalStreamConnection$2$1.onResult(InternalStreamConnection.java:501)
		at com.mongodb.internal.connection.InternalStreamConnection$MessageHeaderCallback$MessageCallback.onResult(InternalStreamConnection.java:824)
		at com.mongodb.internal.connection.InternalStreamConnection$MessageHeaderCallback$MessageCallback.onResult(InternalStreamConnection.java:788)
		at com.mongodb.internal.connection.InternalStreamConnection$5.completed(InternalStreamConnection.java:648)
		at com.mongodb.internal.connection.InternalStreamConnection$5.completed(InternalStreamConnection.java:645)
		at com.mongodb.connection.netty.NettyStream.readAsync(NettyStream.java:319)
		at com.mongodb.connection.netty.NettyStream.handleReadResponse(NettyStream.java:347)
		at com.mongodb.connection.netty.NettyStream.access$1100(NettyStream.java:105)
		at com.mongodb.connection.netty.NettyStream$InboundBufferHandler.channelRead0(NettyStream.java:421)
		at com.mongodb.connection.netty.NettyStream$InboundBufferHandler.channelRead0(NettyStream.java:418)
		at io.netty.channel.SimpleChannelInboundHandler.channelRead(SimpleChannelInboundHandler.java:99)
		at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:444)
		at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420)
		at io.netty.channel.AbstractChannelHandlerContext.fireChannelRead(AbstractChannelHandlerContext.java:412)
		at io.netty.channel.DefaultChannelPipeline$HeadContext.channelRead(DefaultChannelPipeline.java:1410)
		at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:440)
		at io.netty.channel.AbstractChannelHandlerContext.invokeChannelRead(AbstractChannelHandlerContext.java:420)
		at io.netty.channel.DefaultChannelPipeline.fireChannelRead(DefaultChannelPipeline.java:919)
		at io.netty.channel.nio.AbstractNioByteChannel$NioByteUnsafe.read(AbstractNioByteChannel.java:166)
		at io.netty.channel.nio.NioEventLoop.processSelectedKey(NioEventLoop.java:788)
		at io.netty.channel.nio.NioEventLoop.processSelectedKeysOptimized(NioEventLoop.java:724)
		at io.netty.channel.nio.NioEventLoop.processSelectedKeys(NioEventLoop.java:650)
		at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:562)
		at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:997)
		at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
		at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
		at java.base/java.lang.Thread.run(Thread.java:840)
```


---
### workspaceserviceceimpl.java
```java
    // @Override
    // public Mono<Workspace> createDefault(final Workspace workspace, User user) {
    // System.out.println("CREATE DEFAULT");
    // if (LoginSource.FORM.equals(user.getSource())) {
    // // this is a form login
    // // TODO: the workspace name needs to be the user's tenant name
    // workspace.setName("YTI");
    // workspace.setIsAutoGeneratedWorkspace(true);
    // System.out.println("this is a FORM login");
    // return create(workspace, user, TRUE);
    // } else {
    // // this is a SSO login
    // // TODO: find the user and "invite" them to the corresponding workspace
    // System.out.println("this is a SSO login");
    // System.out.printf("workspace name: {}", repository.findByName("YTI"));
    // InviteUsersDTO dto = new InviteUsersDTO();
    //
    // // Initialize the fields using Lombok-generated setters
    // List<String> usernames = Arrays.asList("user1", "user2");
    // String permissionGroupId = "group123";
    //
    // dto.setUsernames(usernames);
    // dto.setPermissionGroupId(permissionGroupId);
    // String originHeader;
    // // TODO: find out what the origin header string is
    // userAndAccessManagementService.inviteUsers(dto, originHeader);
    // return repository.findByName("YTI");
    // }
    // }
```


---
workspace ID
671f737de9580c24533430af