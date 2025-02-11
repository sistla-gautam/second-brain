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

---
## server error
```
backend stdout | [2025-01-27 08:22:34,917] - Error in mongock process. ABORTED MIGRATION
backend stdout | io.mongock.api.exception.MongockException: Error in method[DatabaseChangelog1.addInitialIndexes] : Timeout while receiving message
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processExceptionOnChangeSetExecution(MigrateExecutorBase.java:398)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processSingleChangeSet(MigrateExecutorBase.java:207)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.loopRawChangeSets(MigrateExecutorBase.java:172)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.lambda$processChangeLogInTransactionIfApplies$3(MigrateExecutorBase.java:162)
backend stdout |        at io.mongock.runner.core.executor.NonTransactioner.executeInTransaction(NonTransactioner.java:17)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processChangeLogInTransactionIfApplies(MigrateExecutorBase.java:162)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processSingleChangeLog(MigrateExecutorBase.java:136)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processChangeLogs(MigrateExecutorBase.java:126)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.lambda$processMigration$1(MigrateExecutorBase.java:121)
backend stdout |        at io.mongock.runner.core.executor.NonTransactioner.executeInTransaction(NonTransactioner.java:17)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processMigration(MigrateExecutorBase.java:121)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeMigration(MigrateExecutorBase.java:103)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeMigration(MigrateExecutorBase.java:46)
backend stdout |        at io.mongock.runner.core.executor.MongockRunnerImpl.execute(MongockRunnerImpl.java:53)
backend stdout |        at io.mongock.runner.springboot.base.MongockInitializingBeanRunner.afterPropertiesSet(MongockInitializingBeanRunner.java:17)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.invokeInitMethods(AbstractAutowireCapableBeanFactory.java:1817)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1766)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:598)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:520)
backend stdout |        at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:326)
backend stdout |        at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234)
backend stdout |        at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:324)
backend stdout |        at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:200)
backend stdout |        at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingletons(DefaultListableBeanFactory.java:973)
backend stdout |        at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:942)
backend stdout |        at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:608)
backend stdout |        at org.springframework.boot.web.reactive.context.ReactiveWebServerApplicationContext.refresh(ReactiveWebServerApplicationContext.java:66)
backend stdout |        at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:732)
backend stdout |        at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:434)
backend stdout |        at org.springframework.boot.SpringApplication.run(SpringApplication.java:310)
backend stdout |        at org.springframework.boot.builder.SpringApplicationBuilder.run(SpringApplicationBuilder.java:150)
backend stdout |        at com.appsmith.server.ServerApplication.main(ServerApplication.java:60)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
backend stdout |        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
backend stdout |        at java.base/java.lang.reflect.Method.invoke(Method.java:568)
backend stdout |        at org.springframework.boot.loader.MainMethodRunner.run(MainMethodRunner.java:49)
backend stdout |        at org.springframework.boot.loader.Launcher.launch(Launcher.java:95)
backend stdout |        at org.springframework.boot.loader.Launcher.launch(Launcher.java:58)
backend stdout |        at org.springframework.boot.loader.JarLauncher.main(JarLauncher.java:65)
backend stdout | Caused by: java.lang.reflect.InvocationTargetException: null
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
backend stdout |        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
backend stdout |        at java.base/java.lang.reflect.Method.invoke(Method.java:568)
backend stdout |        at io.mongock.runner.core.executor.ChangeLogRuntimeImpl.runChangeSet(ChangeLogRuntimeImpl.java:79)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeChangeSetMethod(MigrateExecutorBase.java:386)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeAndLogChangeSet(MigrateExecutorBase.java:244)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processSingleChangeSet(MigrateExecutorBase.java:205)
backend stdout |        ... 38 common frames omitted
backend stdout | Caused by: org.springframework.dao.DataAccessResourceFailureException: Timeout while receiving message
backend stdout |        at org.springframework.data.mongodb.core.MongoExceptionTranslator.translateExceptionIfPossible(MongoExceptionTranslator.java:81)
backend stdout |        at org.springframework.data.mongodb.core.MongoTemplate.potentiallyConvertRuntimeException(MongoTemplate.java:2789)
backend stdout |        at org.springframework.data.mongodb.core.MongoTemplate.execute(MongoTemplate.java:555)
backend stdout |        at org.springframework.data.mongodb.core.MongoTemplate.execute(MongoTemplate.java:542)
backend stdout |        at org.springframework.data.mongodb.core.DefaultIndexOperations.execute(DefaultIndexOperations.java:196)
backend stdout |        at org.springframework.data.mongodb.core.DefaultIndexOperations.ensureIndex(DefaultIndexOperations.java:117)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
backend stdout |        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
backend stdout |        at java.base/java.lang.reflect.Method.invoke(Method.java:568)
backend stdout |        at io.mongock.driver.api.lock.guard.proxy.LockGuardProxy.invoke(LockGuardProxy.java:54)
backend stdout |        at io.mongock.driver.api.lock.guard.proxy.LockGuardMethodHandler.invoke(LockGuardMethodHandler.java:25)
backend stdout |        at org.springframework.data.mongodb.core.index.IndexOperations_$$_mongock_6ad_3.ensureIndex(IndexOperations_$$_mongock_6ad_3.java)
backend stdout |        at com.appsmith.server.migrations.DatabaseChangelog1.ensureIndexes(DatabaseChangelog1.java:103)
backend stdout |        at com.appsmith.server.migrations.DatabaseChangelog1.addInitialIndexes(DatabaseChangelog1.java:184)
backend stdout |        ... 46 common frames omitted
backend stdout | Caused by: com.mongodb.MongoSocketReadTimeoutException: Timeout while receiving message
backend stdout |        at com.mongodb.connection.netty.NettyStream$InboundBufferHandler.exceptionCaught(NettyStream.java:427)
backend stdout |        at io.netty.channel.AbstractChannelHandlerContext.invokeExceptionCaught(AbstractChannelHandlerContext.java:346)
backend stdout |        at io.netty.channel.AbstractChannelHandlerContext.invokeExceptionCaught(AbstractChannelHandlerContext.java:325)
backend stdout |        at io.netty.channel.AbstractChannelHandlerContext.fireExceptionCaught(AbstractChannelHandlerContext.java:317)
backend stdout |        at com.mongodb.connection.netty.NettyStream$ReadTimeoutTask.run(NettyStream.java:564)
backend stdout |        at io.netty.util.concurrent.PromiseTask.runTask(PromiseTask.java:98)
backend stdout |        at io.netty.util.concurrent.ScheduledFutureTask.run(ScheduledFutureTask.java:153)
backend stdout |        at io.netty.util.concurrent.AbstractEventExecutor.runTask(AbstractEventExecutor.java:174)
backend stdout |        at io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java:167)
backend stdout |        at io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:470)
backend stdout |        at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:569)
backend stdout |        at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:997)
backend stdout |        at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
backend stdout |        at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
backend stdout |        at java.base/java.lang.Thread.run(Thread.java:840)
backend stdout | Caused by: io.netty.handler.timeout.ReadTimeoutException: null
backend stdout | [2025-01-27 08:22:39,127] - Application run failed
backend stdout | org.springframework.beans.factory.BeanCreationException: Error creating bean with name 'mongockInitializingBeanRunner' defined in class path resource [com/appsmith/server/configurations/MongoConfig.class]: Error in method[DatabaseChangelog1.addInitialIndexes] : Timeout while receiving message
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1770)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.doCreateBean(AbstractAutowireCapableBeanFactory.java:598)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.createBean(AbstractAutowireCapableBeanFactory.java:520)
backend stdout |        at org.springframework.beans.factory.support.AbstractBeanFactory.lambda$doGetBean$0(AbstractBeanFactory.java:326)
backend stdout |        at org.springframework.beans.factory.support.DefaultSingletonBeanRegistry.getSingleton(DefaultSingletonBeanRegistry.java:234)
backend stdout |        at org.springframework.beans.factory.support.AbstractBeanFactory.doGetBean(AbstractBeanFactory.java:324)
backend stdout |        at org.springframework.beans.factory.support.AbstractBeanFactory.getBean(AbstractBeanFactory.java:200)
backend stdout |        at org.springframework.beans.factory.support.DefaultListableBeanFactory.preInstantiateSingletons(DefaultListableBeanFactory.java:973)
backend stdout |        at org.springframework.context.support.AbstractApplicationContext.finishBeanFactoryInitialization(AbstractApplicationContext.java:942)
backend stdout |        at org.springframework.context.support.AbstractApplicationContext.refresh(AbstractApplicationContext.java:608)
backend stdout |        at org.springframework.boot.web.reactive.context.ReactiveWebServerApplicationContext.refresh(ReactiveWebServerApplicationContext.java:66)
backend stdout |        at org.springframework.boot.SpringApplication.refresh(SpringApplication.java:732)
backend stdout |        at org.springframework.boot.SpringApplication.refreshContext(SpringApplication.java:434)
backend stdout |        at org.springframework.boot.SpringApplication.run(SpringApplication.java:310)
backend stdout |        at org.springframework.boot.builder.SpringApplicationBuilder.run(SpringApplicationBuilder.java:150)
backend stdout |        at com.appsmith.server.ServerApplication.main(ServerApplication.java:60)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
backend stdout |        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
backend stdout |        at java.base/java.lang.reflect.Method.invoke(Method.java:568)
backend stdout |        at org.springframework.boot.loader.MainMethodRunner.run(MainMethodRunner.java:49)
backend stdout |        at org.springframework.boot.loader.Launcher.launch(Launcher.java:95)
backend stdout |        at org.springframework.boot.loader.Launcher.launch(Launcher.java:58)
backend stdout |        at org.springframework.boot.loader.JarLauncher.main(JarLauncher.java:65)
backend stdout | Caused by: io.mongock.api.exception.MongockException: Error in method[DatabaseChangelog1.addInitialIndexes] : Timeout while receiving message
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processExceptionOnChangeSetExecution(MigrateExecutorBase.java:398)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processSingleChangeSet(MigrateExecutorBase.java:207)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.loopRawChangeSets(MigrateExecutorBase.java:172)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.lambda$processChangeLogInTransactionIfApplies$3(MigrateExecutorBase.java:162)
backend stdout |        at io.mongock.runner.core.executor.NonTransactioner.executeInTransaction(NonTransactioner.java:17)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processChangeLogInTransactionIfApplies(MigrateExecutorBase.java:162)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processSingleChangeLog(MigrateExecutorBase.java:136)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processChangeLogs(MigrateExecutorBase.java:126)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.lambda$processMigration$1(MigrateExecutorBase.java:121)
backend stdout |        at io.mongock.runner.core.executor.NonTransactioner.executeInTransaction(NonTransactioner.java:17)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processMigration(MigrateExecutorBase.java:121)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeMigration(MigrateExecutorBase.java:103)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeMigration(MigrateExecutorBase.java:46)
backend stdout |        at io.mongock.runner.core.executor.MongockRunnerImpl.execute(MongockRunnerImpl.java:53)
backend stdout |        at io.mongock.runner.springboot.base.MongockInitializingBeanRunner.afterPropertiesSet(MongockInitializingBeanRunner.java:17)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.invokeInitMethods(AbstractAutowireCapableBeanFactory.java:1817)
backend stdout |        at org.springframework.beans.factory.support.AbstractAutowireCapableBeanFactory.initializeBean(AbstractAutowireCapableBeanFactory.java:1766)
backend stdout |        ... 23 common frames omitted
backend stdout | Caused by: java.lang.reflect.InvocationTargetException: null
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
backend stdout |        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
backend stdout |        at java.base/java.lang.reflect.Method.invoke(Method.java:568)
backend stdout |        at io.mongock.runner.core.executor.ChangeLogRuntimeImpl.runChangeSet(ChangeLogRuntimeImpl.java:79)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeChangeSetMethod(MigrateExecutorBase.java:386)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.executeAndLogChangeSet(MigrateExecutorBase.java:244)
backend stdout |        at io.mongock.runner.core.executor.operation.migrate.MigrateExecutorBase.processSingleChangeSet(MigrateExecutorBase.java:205)
backend stdout |        ... 38 common frames omitted
backend stdout | Caused by: org.springframework.dao.DataAccessResourceFailureException: Timeout while receiving message
backend stdout |        at org.springframework.data.mongodb.core.MongoExceptionTranslator.translateExceptionIfPossible(MongoExceptionTranslator.java:81)
backend stdout |        at org.springframework.data.mongodb.core.MongoTemplate.potentiallyConvertRuntimeException(MongoTemplate.java:2789)
backend stdout |        at org.springframework.data.mongodb.core.MongoTemplate.execute(MongoTemplate.java:555)
backend stdout |        at org.springframework.data.mongodb.core.MongoTemplate.execute(MongoTemplate.java:542)
backend stdout |        at org.springframework.data.mongodb.core.DefaultIndexOperations.execute(DefaultIndexOperations.java:196)
backend stdout |        at org.springframework.data.mongodb.core.DefaultIndexOperations.ensureIndex(DefaultIndexOperations.java:117)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
backend stdout |        at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)
backend stdout |        at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
backend stdout |        at java.base/java.lang.reflect.Method.invoke(Method.java:568)
backend stdout |        at io.mongock.driver.api.lock.guard.proxy.LockGuardProxy.invoke(LockGuardProxy.java:54)
backend stdout |        at io.mongock.driver.api.lock.guard.proxy.LockGuardMethodHandler.invoke(LockGuardMethodHandler.java:25)
backend stdout |        at org.springframework.data.mongodb.core.index.IndexOperations_$$_mongock_6ad_3.ensureIndex(IndexOperations_$$_mongock_6ad_3.java)
backend stdout |        at com.appsmith.server.migrations.DatabaseChangelog1.ensureIndexes(DatabaseChangelog1.java:103)
backend stdout |        at com.appsmith.server.migrations.DatabaseChangelog1.addInitialIndexes(DatabaseChangelog1.java:184)
backend stdout |        ... 46 common frames omitted
backend stdout | Caused by: com.mongodb.MongoSocketReadTimeoutException: Timeout while receiving message
backend stdout |        at com.mongodb.connection.netty.NettyStream$InboundBufferHandler.exceptionCaught(NettyStream.java:427)
backend stdout |        at io.netty.channel.AbstractChannelHandlerContext.invokeExceptionCaught(AbstractChannelHandlerContext.java:346)
backend stdout |        at io.netty.channel.AbstractChannelHandlerContext.invokeExceptionCaught(AbstractChannelHandlerContext.java:325)
backend stdout |        at io.netty.channel.AbstractChannelHandlerContext.fireExceptionCaught(AbstractChannelHandlerContext.java:317)
backend stdout |        at com.mongodb.connection.netty.NettyStream$ReadTimeoutTask.run(NettyStream.java:564)
backend stdout |        at io.netty.util.concurrent.PromiseTask.runTask(PromiseTask.java:98)
backend stdout |        at io.netty.util.concurrent.ScheduledFutureTask.run(ScheduledFutureTask.java:153)
backend stdout |        at io.netty.util.concurrent.AbstractEventExecutor.runTask(AbstractEventExecutor.java:174)
backend stdout |        at io.netty.util.concurrent.AbstractEventExecutor.safeExecute(AbstractEventExecutor.java:167)
backend stdout |        at io.netty.util.concurrent.SingleThreadEventExecutor.runAllTasks(SingleThreadEventExecutor.java:470)
backend stdout |        at io.netty.channel.nio.NioEventLoop.run(NioEventLoop.java:569)
backend stdout |        at io.netty.util.concurrent.SingleThreadEventExecutor$4.run(SingleThreadEventExecutor.java:997)
backend stdout |        at io.netty.util.internal.ThreadExecutorMap$2.run(ThreadExecutorMap.java:74)
backend stdout |        at io.netty.util.concurrent.FastThreadLocalRunnable.run(FastThreadLocalRunnable.java:30)
backend stdout |        at java.base/java.lang.Thread.run(Thread.java:840)
backend stdout | Caused by: io.netty.handler.timeout.ReadTimeoutException: null
editor stderr | {"level":"debug","ts":1737966192.407822,"logger":"http.handlers.reverse_proxy","msg":"selected upstream","dial":"127.0.0.1:8080","total_upstreams":1}
editor stderr | {"level":"debug","ts":1737966192.4081452,"logger":"http.handlers.reverse_proxy","msg":"upstream roundtrip","upstream":"127.0.0.1:8080","duration":0.000205402,"request":{"remote_ip":"10.202.4.77","remote_port":"55706","client_ip":"10.202.4.77","proto":"HTTP/1.1","method":"GET","host":"10.202.4.169:80","uri":"/api/v1/health","headers":{"User-Agent":["kube-probe/1.29"],"Accept":["*/*"],"X-Appsmith-Request-Id":["782c205f-6c6a-4099-9f5a-c598c0ff77dd"],"X-Forwarded-For":["10.202.4.77"],"X-Request-Id":["invalid_request_id"],"X-Forwarded-Proto":["http"],"X-Forwarded-Host":["10.202.4.169:80"]}},"error":"dial tcp 127.0.0.1:8080: connect: connection refused"}
editor stderr | {"level":"debug","ts":1737966192.4082398,"logger":"http.log.error.log0","msg":"dial tcp 127.0.0.1:8080: connect: connection refused","request":{"remote_ip":"10.202.4.77","remote_port":"55706","client_ip":"10.202.4.77","proto":"HTTP/1.1","method":"GET","host":"10.202.4.169:80","uri":"/api/v1/health","headers":{"Accept":["*/*"],"Connection":["close"],"User-Agent":["kube-probe/1.29"]}},"duration":0.000561806,"status":502,"err_id":"z9sucqwji","err_trace":"reverseproxy.statusError (reverseproxy.go:1373)"}
editor stderr | {"level":"debug","ts":1737966252.4077168,"logger":"http.handlers.reverse_proxy","msg":"selected upstream","dial":"127.0.0.1:8080","total_upstreams":1}
editor stderr | {"level":"debug","ts":1737966252.4079854,"logger":"http.handlers.reverse_proxy","msg":"upstream roundtrip","upstream":"127.0.0.1:8080","duration":0.000160402,"request":{"remote_ip":"10.202.4.77","remote_port":"44140","client_ip":"10.202.4.77","proto":"HTTP/1.1","method":"GET","host":"10.202.4.169:80","uri":"/api/v1/health","headers":{"User-Agent":["kube-probe/1.29"],"Accept":["*/*"],"X-Appsmith-Request-Id":["557c3131-2575-46d4-a149-52f6b3938c2f"],"X-Forwarded-For":["10.202.4.77"],"X-Request-Id":["invalid_request_id"],"X-Forwarded-Proto":["http"],"X-Forwarded-Host":["10.202.4.169:80"]}},"error":"dial tcp 127.0.0.1:8080: connect: connection refused"}
editor stderr | {"level":"debug","ts":1737966252.4080727,"logger":"http.log.error.log0","msg":"dial tcp 127.0.0.1:8080: connect: connection refused","request":{"remote_ip":"10.202.4.77","remote_port":"44140","client_ip":"10.202.4.77","proto":"HTTP/1.1","method":"GET","host":"10.202.4.169:80","uri":"/api/v1/health","headers":{"User-Agent":["kube-probe/1.29"],"Accept":["*/*"],"Connection":["close"]}},"duration":0.000435904,"status":502,"err_id":"wvjkiyhpn","err_trace":"reverseproxy.statusError (reverseproxy.go:1373)"}
```