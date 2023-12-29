# Svelte Simple Accordion

A simple Accordion component for Svelte.

## Usage:

    <script>    
    import { Accordion, AccordionItem } from '@gratrockstar/svelte-simple-accordion';
    
    const items = [    
	    { title: 'Item 1', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Curabitur sagittis malesuada lorem, non finibus sapien rutrum sed. Curabitur eget dictum turpis, nec malesuada elit. Phasellus eu fringilla lacus. Suspendisse convallis mi sed felis consequat, ac varius nisl ullamcorper. Nullam faucibus mi at est ullamcorper ultrices. Ut et diam ut enim iaculis mollis quis non mauris. Phasellus odio metus, viverra et egestas vitae, hendrerit in erat. Donec vitae magna nec dolor tempor interdum scelerisque id nunc. Quisque faucibus lectus varius erat sollicitudin aliquet. Quisque id massa sed tellus tincidunt auctor. Praesent quis faucibus nunc. Fusce vel ipsum elit. Proin enim nunc, sagittis in cursus nec, molestie laoreet diam. Phasellus scelerisque lectus et condimentum efficitur. Vestibulum aliquam lorem vitae laoreet elementum. Fusce lorem urna, sagittis vel lacinia aliquet, consequat sed urna' },	    
	    { title: 'Item 2', content: 'Morbi risus ante, ornare vel nulla quis, finibus viverra ante. In hac habitasse platea dictumst. Morbi dignissim massa malesuada, dignissim urna et, consequat leo. Vivamus velit orci, hendrerit in sapien sed, suscipit rutrum urna. Vestibulum eget semper mi. Nunc semper ultricies felis, eu faucibus elit. Etiam id lobortis nibh, id facilisis velit. Donec vitae aliquet mauris. Sed vel justo ut odio rutrum pretium.' },	    
	    { title: 'Item 3', content: 'urpis sed sem congue, id efficitur orci commodo. Nulla commodo orci non pharetra fermentum. Pellentesque non arcu enim. Mauris ut neque purus. Sed tristique mi velit, et hendrerit nibh vestibulum non. Proin molestie sapien ac odio convallis, ac congue mi tincidunt. Duis aliquet tortor non tortor pretium, vitae auctor libero fermentum. Nullam nec pretium lectus, a pulvinar tellus.' },	    
	    { title: 'Item 4', content: 'Cras ante felis, ultrices eu sapien eu, venenatis luctus sem. Suspendisse faucibus, massa ac tempor dapibus, ligula justo pretium turpis, consectetur condimentum diam purus venenatis quam. Curabitur vel quam hendrerit, blandit purus et, euismod nulla. Nulla in tristique purus. Maecenas vehicula feugiat condimentum. Integer fringilla nulla ut urna consequat auctor. Curabitur volutpat eu orci sed lobortis. Sed tellus magna, vehicula et augue tempor, vestibulum ullamcorper libero. Donec eros sapien, interdum et lectus quis, dapibus eleifend enim. Nullam mi augue, iaculis ac velit ac, sagittis feugiat erat. Vivamus nec nulla a dolor sodales bibendum congue vitae enim. Aenean lacinia finibus massa, ac tempus augue hendrerit in. Phasellus sit amet turpis ut massa tristique laoreet. Etiam id arcu sed sapien imperdiet vulputate. Vestibulum porta erat quis quam feugiat, id dapibus est sollicitudin. Vestibulum mauris tellus, ullamcorper tincidunt porta id, luctus eu enim.' }    
    ]    
    </script>
    
    <Accordion collapse --accordion-width="100%">    
	    {#each items as item, i}    
	    <AccordionItem open={i === 0}>    
		    <svelte:fragment slot="title">{item.title}</svelte:fragment>    
		    <svelte:fragment slot="content">{item.content}</svelte:fragment>    
	    </AccordionItem>   
	    {/each}    
    </Accordion>
