<script lang="ts">
	import { onMount } from 'svelte';
	import Logo from './logo.svelte';
	import Theme from './theme.svelte';
	import Cpu from './cpu.svelte';
	import CpuCooler from './cpuCooler.svelte';
	let component: typeof Cpu | typeof CpuCooler = Cpu;
</script>

<svelte:head>
	<title>Home</title>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
	<meta name="description" content="" />
</svelte:head>

<Theme />
<!-- Modal -->
<div
	class="modal fade"
	id="modal01"
	tabindex="-1"
	aria-labelledby="cpuModalLabel"
	aria-hidden="true"
>
	<div class="modal-dialog modal-dialog-scrollable modal-xl">
		<div class="modal-content"><svelte:component this={component} /></div>
	</div>
</div>
<div class="container">
	<main>
		<div class="py-5 text-center">
			<Logo />
			<h2>自作PC構成見積もり</h2>
			<p class="lead">
				自作パソコンのパーツ構成をシミュレートしつつ見積もりを作るサイトです。<br />
				クリックしてパーツを検索/選択すると見積もりが作成できます。
			</p>
		</div>

		<div class="row g-5">
			<div class="col">
				<h4 class="d-flex justify-content-between align-items-center mb-3">
					<span class="text-primary">PCパーツ一覧</span>
					<span class="badge bg-primary rounded-pill">3</span>
				</h4>
				<ul class="list-group mb-3">
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button
								class="btn btn-secondary"
								data-bs-toggle="modal"
								data-bs-target="#modal01"
								on:click={() => {
									component = Cpu;
								}}>CPU</button
							>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$12</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button
								class="btn btn-secondary"
								data-bs-toggle="modal"
								data-bs-target="#modal01"
								on:click={() => {
									component = CpuCooler;
								}}>CPUクーラー</button
							>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$8</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">メモリー</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">マザーボード</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">ビデオカード</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">SSD</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">HDD</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">ケース</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">電源</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">OS</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">サウンド</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between lh-sm">
						<div>
							<button class="btn btn-secondary">光学ドライブ</button>
							<small class="text-body-secondary">Brief description</small>
						</div>
						<span class="text-body-secondary">$5</span>
					</li>
					<li class="list-group-item d-flex justify-content-between bg-body-tertiary">
						<div class="text-success">
							<h6 class="my-0">割引/調整など</h6>
							<small>EXAMPLECODE</small>
						</div>
						<span class="text-success">−\0</span>
					</li>
					<li class="list-group-item d-flex justify-content-between">
						<span>Total (YEN)</span>
						<strong>\20</strong>
					</li>
				</ul>
			</div>
		</div>
	</main>

	<footer class="my-5 pt-5 text-body-secondary text-center text-small">
		<p class="mb-1">&copy; 2017–2023 Company Name</p>
		<ul class="list-inline" />
	</footer>
</div>

<style>
</style>
